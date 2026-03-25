---
title: "Worklog Tuần 4"
date: 2026-01-26
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu Tuần 4

Tuần này tập trung vào việc vận hành hệ thống theo định hướng thực tế hơn, hướng đến mô hình production-ready. Nội dung chính bao gồm tự động hóa, bảo mật, độ tin cậy, hiệu năng và tối ưu chi phí dựa trên AWS Well-Architected Framework.

- **Vận hành (Operational Excellence)**:
  - Tự động hóa các tác vụ bằng AWS Lambda, như tắt EC2 và gửi thông báo qua Slack
  - Xây dựng hệ thống giám sát với CloudWatch và Grafana
  - Quản lý tài nguyên EC2 thông qua Tags
  - Tự động hóa vận hành bằng AWS Systems Manager

- **Bảo mật (Security)**:
  - Áp dụng IAM Permission Boundary để kiểm soát và giới hạn quyền
  - Kiểm tra và đánh giá bảo mật với AWS Security Hub
  - Bảo vệ ứng dụng bằng AWS WAF

- **Độ tin cậy (Reliability)**:
  - Thiết lập cơ chế sao lưu với AWS Backup
  - Kết nối các VPC thông qua VPC Peering
  - Quản lý kết nối mạng tập trung bằng Transit Gateway

- **Hiệu năng (Performance Efficiency)**:
  - Container hóa ứng dụng bằng Docker và triển khai trên ECS
  - Xây dựng quy trình CI/CD với CodePipeline
  - Lưu trữ dữ liệu thông qua File Storage Gateway

- **Tối ưu chi phí (Cost Optimization)**:
  - Áp dụng Savings Plans và Reserved Instances
  - Thực hiện right-sizing cho EC2
  - Theo dõi và trực quan hóa chi phí sử dụng

---

### Tổng quan công việc

| Ngày | Nhiệm vụ                                                                                                     | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                  |
| :--: | ------------------------------------------------------------------------------------------------------------ | :----------: | :-------------: | --------------------------------------------------- |
|  1   | **Automation & Monitoring**:<br>- AWS Lambda<br>- CloudWatch + Grafana<br>- EC2 Tagging<br>- Systems Manager |  26/01/2026  |   26/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  2   | **Security**:<br>- IAM Permission Boundary<br>- Security Hub<br>- AWS WAF                                    |  27/01/2026  |   27/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  3   | **Reliability**:<br>- AWS Backup<br>- VPC Peering<br>- Transit Gateway                                       |  28/01/2026  |   28/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  4   | **Performance**:<br>- Docker + ECS<br>- CodePipeline<br>- File Storage Gateway                               |  29/01/2026  |   29/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  5   | **Cost Optimization**:<br>- Savings Plans<br>- Reserved Instances<br>- Cost Visualization                    |  30/01/2026  |   30/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |

---

### Kết quả đạt được

#### Những gì đã hoàn thành

- Tự động hóa quy trình vận hành:
  - Tự động tắt EC2 và gửi thông báo bằng Lambda
  - Xây dựng dashboard giám sát bằng CloudWatch và Grafana
  - Quản lý tài nguyên bằng Tags và Systems Manager

- Tăng cường bảo mật hệ thống:
  - Áp dụng **IAM Permission Boundary**
  - Triển khai **AWS WAF**
  - Thực hiện kiểm tra bảo mật với **Security Hub**

- Cải thiện độ tin cậy:
  - Thiết lập backup tự động bằng **AWS Backup**
  - Xây dựng kết nối mạng ổn định với **VPC Peering** và **Transit Gateway**

- Nâng cao hiệu năng:
  - Triển khai ứng dụng container với **Docker và ECS**
  - Xây dựng pipeline **CI/CD**

- Tối ưu chi phí vận hành:
  - Áp dụng **Savings Plans** và **Reserved Instances**
  - Thực hiện **right-sizing EC2**
  - Theo dõi và phân tích chi phí sử dụng

#### Tóm tắt kiến trúc

- **Automation**: Lambda + Systems Manager
- **Monitoring**: CloudWatch + Grafana
- **Security**: IAM Boundary + WAF + Security Hub
- **Networking**: VPC Peering + Transit Gateway
- **Compute**: ECS (Docker containers)
- **CI/CD**: CodePipeline
- **Storage**: File Storage Gateway
- **Cost**: Savings Plans + Cost Monitoring
