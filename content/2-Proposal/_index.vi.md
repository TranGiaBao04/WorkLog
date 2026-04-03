---
title: "Proposal"
date: 2026-03-24
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Hệ thống quản lý trạm sạc xe điện

## Nền tảng backend thông minh cho vận hành trạm sạc và thanh toán số

### 1. Tóm tắt điều hành

Hệ thống quản lý trạm sạc xe điện là một nền tảng backend tập trung được xây dựng nhằm hỗ trợ toàn bộ vòng đời vận hành của dịch vụ sạc xe điện. Hệ thống bao phủ các nghiệp vụ cốt lõi như tìm kiếm trạm sạc, quản lý khung giờ, tạo và xác nhận đặt chỗ, theo dõi phiên sạc, tạo hóa đơn, xử lý thanh toán và quản lý tuân thủ của tài xế trong một nền tảng thống nhất.

Hệ thống được triển khai trên kiến trúc AWS Cloud hiện đại theo mô hình phân lớp (Edge Layer – Application Layer – Data Layer – Observability & Security), đảm bảo hiệu năng cao, bảo mật và khả năng mở rộng linh hoạt.

Kiến trúc sử dụng CloudFront CDN kết hợp WAF để phân phối nội dung và bảo vệ hệ thống, Application Load Balancer và Auto Scaling Group để xử lý tải động, cùng với Amazon RDS Multi-AZ đảm bảo tính sẵn sàng cao cho dữ liệu. Ngoài ra, các dịch vụ như Secrets Manager, KMS, CloudWatch, CloudTrail và SES giúp tăng cường bảo mật, giám sát và vận hành hệ thống trong môi trường production.

Giải pháp phù hợp với các hệ thống EV quy mô lớn cần độ ổn định cao, khả năng mở rộng và bảo mật theo tiêu chuẩn cloud hiện đại.

---

### 2. Bài toán đặt ra

#### Vấn đề hiện tại là gì?

Trong bối cảnh thị trường xe điện phát triển nhanh, các hệ thống quản lý trạm sạc thường gặp các vấn đề:

- Khó mở rộng khi lượng người dùng tăng nhanh
- Hệ thống dễ bị quá tải do thiếu load balancing
- Database trở thành điểm lỗi đơn (single point of failure)
- Thiếu lớp bảo mật (WAF, secrets management)
- Backend expose trực tiếp ra Internet gây rủi ro bảo mật
- Thiếu hệ thống giám sát và logging

#### Giải pháp đề xuất

Giải pháp là xây dựng hệ thống backend trên AWS theo kiến trúc chuẩn production với:

- Route 53 + CloudFront + WAF cho tầng Edge
- S3 lưu trữ frontend (private + OAC)
- ALB + EC2 private subnet + Auto Scaling cho backend
- NAT Gateway cho outbound traffic
- RDS Multi-AZ cho database
- Secrets Manager + KMS cho bảo mật
- CloudWatch + CloudTrail cho monitoring
- SES cho email service
- SSM cho quản trị hệ thống

---

### 3. Kiến trúc giải pháp

Hệ thống được thiết kế theo mô hình phân lớp, triển khai trên VPC với nhiều Availability Zone để đảm bảo tính sẵn sàng cao và khả năng mở rộng.

![EV Charging System Architecture](/images/2-Proposal/AWS-architecture.png)

#### Mô hình kiến trúc AWS theo luồng xử lý

**(1) User → Internet**  
Người dùng truy cập hệ thống thông qua trình duyệt hoặc ứng dụng.

**(2) Internet → Route 53**  
Route 53 thực hiện phân giải DNS và điều hướng request.

**(3) Route 53 → CloudFront + WAF**  
CloudFront phân phối nội dung và WAF kiểm tra request nhằm ngăn chặn tấn công.

**(4) Frontend → Amazon Location Service**  
Frontend gọi API map để hiển thị vị trí trạm sạc.

**(5) CloudFront → Amazon S3 (Frontend)**  
CloudFront lấy tài nguyên tĩnh từ S3 thông qua OAC.

---

**(6) CloudFront → ALB**  
CloudFront forward API request đến Application Load Balancer.

**(7) ALB → EC2 (Private Subnet - AZ1)**  
ALB phân phối request đến EC2 instance.

**(8) Auto Scaling Group (AZ1 ↔ AZ2)**  
EC2 instances được scale tự động và chạy đa AZ.

---

**(9) EC2 → Amazon RDS (Primary/Standby)**  
Backend truy vấn database RDS Multi-AZ.

---

**(10) EC2 → NAT Gateway → Internet**  
EC2 gọi ra external services thông qua NAT Gateway.

**(11) EC2 (AZ2) → RDS**  
Instance ở AZ2 đảm bảo khả năng failover.

---

**(12) NAT Gateway → Internet Gateway**  
Cho phép outbound traffic.

**(13) Internet Gateway → Internet**  
Kết nối ra bên ngoài.

---

### Tầng Data Layer

- Amazon RDS for SQL Server (Multi-AZ)
- Không public access
- Tự động failover

---

### Tầng Observability & Security

**(14) EC2 → Amazon SES**  
Gửi email hệ thống.

**(15) EC2 → Secrets Manager + KMS**  
Lấy secrets và giải mã dữ liệu.

**(16) Admin → AWS Systems Manager (SSM)**  
Quản trị EC2 an toàn, không cần SSH.

**(17) Response → CloudFront → User**  
Trả response về client.

---

| Thành phần     | Dịch vụ / Công nghệ  |
| -------------- | -------------------- |
| DNS            | Route 53             |
| CDN            | CloudFront           |
| Security       | WAF                  |
| Frontend       | S3                   |
| Backend        | EC2 (Private Subnet) |
| Load balancing | ALB                  |
| Scaling        | Auto Scaling Group   |
| Database       | RDS Multi-AZ         |
| Monitoring     | CloudWatch           |
| Logging        | CloudTrail           |
| Secrets        | Secrets Manager      |
| Encryption     | KMS                  |
| Email          | SES                  |
| Admin Access   | AWS SSM              |

---

### 4. Triển khai kỹ thuật

#### Cách tiếp cận xử lý nghiệp vụ

Hệ thống sử dụng Spring Boot backend kết hợp JWT authentication.

Luồng hoạt động:

1. User request → Route 53 → CloudFront
2. CloudFront kiểm tra WAF
3. CloudFront lấy frontend từ S3
4. API request → ALB → EC2
5. Backend verify JWT
6. Backend xử lý business logic
7. Backend truy vấn RDS
8. Backend gọi external service qua NAT Gateway
9. Backend gửi email qua SES
10. Response trả về CloudFront → User

#### Yêu cầu kỹ thuật

- Frontend: S3 + CloudFront
- Backend: Spring Boot (Java 17)
- Authentication: JWT
- Database: RDS SQL Server
- Load balancing: ALB
- Scaling: Auto Scaling
- Security: WAF + Secrets Manager + KMS
- Monitoring: CloudWatch + CloudTrail
- Email: SES
- Admin: AWS SSM

---

### 5. Kế hoạch triển khai

- Tuần 7–8: Thiết kế kiến trúc AWS + VPC
- Tuần 8–9: Triển khai backend + database
- Tuần 9–10: Tích hợp payment + email + map
- Tuần 10–11: Bảo mật + monitoring + scaling
- Tuần 12: Deploy production

---

### 6. Dự toán chi phí

| Thành phần | Dịch vụ             | Chi phí          |
| ---------- | ------------------- | ---------------- |
| Frontend   | S3 + CloudFront     | Thấp             |
| Backend    | EC2 + ALB           | Trung bình       |
| Database   | RDS Multi-AZ        | Trung bình – cao |
| Security   | WAF + KMS + Secrets | Thấp             |
| Monitoring | CloudWatch          | Thấp             |
| Email      | SES                 | Thấp             |

---

### 7. Đánh giá rủi ro

#### Rủi ro

- Quá tải hệ thống
- Lỗi payment
- Lộ secrets
- Lỗi cấu hình cloud

#### Giải pháp

- Auto Scaling
- Retry logic
- Secrets Manager
- CloudWatch monitoring

---

### 8. Kết quả kỳ vọng

#### Cải tiến kỹ thuật

- High availability
- Secure system
- Scalable architecture
- Monitoring đầy đủ

#### Giá trị dài hạn

- Sẵn sàng production
- Dễ mở rộng
- Tăng trải nghiệm người dùng
