---
title: "Worklog Tuần 2"
date: 2026-01-12
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu Tuần 2

Trong tuần này, trọng tâm là củng cố kiến thức nền tảng về quản lý quyền truy cập và kiến trúc mạng trên AWS, từ các khái niệm cơ bản đến những nội dung nâng cao hơn. Các mục tiêu chính gồm:

- **Quản lý IAM**:
  - Tạo người dùng và nhóm
  - Gán các policy phù hợp
  - Tạo và sử dụng IAM Role
  - Thực hành chuyển đổi quyền bằng **Switch Role**

- **Nắm chắc VPC Networking**:
  - Hiểu tổng quan về kiến trúc VPC
  - Phân biệt **Security Groups và Network ACLs**
  - Chuẩn bị môi trường mạng phục vụ cho EC2

- **Triển khai EC2**:
  - Khởi tạo EC2 trong subnet
  - Cấu hình Security Group
  - Kết nối SSH bằng Key Pair

- **Cấu hình Hybrid DNS với Route 53 Resolver**:
  - Tạo Key Pair
  - Thiết lập Security Group
  - Cấu hình DNS:
    - Tạo Outbound Endpoint
    - Tạo Resolver Rules
    - Tạo Inbound Endpoint
  - Dọn dẹp tài nguyên sau khi hoàn tất

- **Thiết lập VPC Peering**:
  - Tìm hiểu cơ chế hoạt động của Peering
  - Sử dụng CloudFormation để khởi tạo hạ tầng
  - Tạo Security Group và EC2
  - Cập nhật Network ACLs
  - Thiết lập Peering Connection
  - Cập nhật Route Tables
  - Bật tính năng Cross-Peer DNS

- **Triển khai AWS Transit Gateway**:
  - Tạo Transit Gateway
  - Tạo Attachments cho các VPC
  - Cấu hình Route Tables cho Transit Gateway
  - Cập nhật Route Tables của từng VPC

---

### Tổng quan công việc

| Ngày | Nhiệm vụ                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                   |
| :--: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------: | :-------------: | -------------------------------------------------------------------- |
|  1   | **IAM & EC2 cơ bản**:<br>- Tạo Users và Groups<br>- Gắn Policies<br>- Tạo Role và thực hành Switch Role<br>- Khởi tạo EC2 và kết nối SSH                   |  12/01/2026  |   12/01/2026    | [AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj/) |
|  2   | **VPC Networking**:<br>- Tìm hiểu tổng quan VPC<br>- So sánh Security Group và NACL<br>- Chuẩn bị subnet cho EC2                                           |  13/01/2026  |   13/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/)                  |
|  3   | **Hybrid DNS (Route 53 Resolver)**:<br>- Tạo Key Pair<br>- Cấu hình Security Group<br>- Tạo Outbound / Inbound Endpoint<br>- Tạo Resolver Rules            |  14/01/2026  |   14/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/)                  |
|  4   | **VPC Peering**:<br>- Xây dựng CloudFormation Template<br>- Tạo EC2 và Security Group<br>- Thiết lập Peering<br>- Cập nhật Route Tables<br>- Kích hoạt DNS |  15/01/2026  |   15/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/)                  |
|  5   | **Transit Gateway**:<br>- Tạo TGW<br>- Gắn VPC vào TGW<br>- Cấu hình Route Tables                                                                          |  16/01/2026  |   16/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/)                  |

---

### Kết quả đạt được

#### Những gì đã hoàn thành

- Hiểu rõ hơn về cơ chế phân quyền trong **IAM** và thực hành thành công **Switch Role**
- Nắm được kiến trúc mạng **VPC** cùng cơ chế bảo mật bằng Security Group
- Triển khai thành công **EC2** và thực hiện kết nối SSH
- Cấu hình thành công **Hybrid DNS** với Route 53 Resolver
- Thiết lập **VPC Peering** để kết nối giữa môi trường Dev và Staging
- Triển khai **AWS Transit Gateway** làm điểm trung tâm kết nối nhiều VPC
- Làm quen với mô hình **Infrastructure as Code** thông qua CloudFormation
- Thực hiện **dọn dẹp tài nguyên** sau khi hoàn tất bài thực hành

#### Tóm tắt kiến trúc

- **Phân quyền IAM**: Users → Groups → Policies → Roles
- **Mạng VPC**:
  - Security Group: kiểm soát ở mức instance
  - NACL: kiểm soát ở mức subnet
- **Hybrid DNS**:
  - Kết nối DNS giữa on-premises và AWS thông qua Route 53 Resolver
- **Kết nối mạng**:
  - VPC Peering: kết nối point-to-point
  - Transit Gateway: mô hình hub-and-spoke
