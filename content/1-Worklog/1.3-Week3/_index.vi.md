---
title: "Worklog Tuần 3"
date: 2026-01-19
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu Tuần 3

Trong tuần này, trọng tâm là phát triển ý tưởng cho dự án cuối kỳ và thực hành các dịch vụ cốt lõi của AWS như EC2, S3, IAM và RDS. Các mục tiêu chính bao gồm:

- **Phát triển dự án cuối kỳ**:
  - Xây dựng ý tưởng cho dự án
  - Phân tích và lựa chọn các dịch vụ AWS phù hợp
  - Phác thảo kiến trúc ban đầu

- **Thực hành với EC2**:
  - Tìm hiểu về dịch vụ EC2
  - Triển khai máy ảo
  - Cấu hình instance
  - Tạo và sử dụng AMI tùy chỉnh

- **Quản lý truy cập và môi trường phát triển**:
  - Tìm hiểu và thực hành IAM Role
  - Làm quen với Cloud9

- **Lưu trữ và quản lý dữ liệu**:
  - Cấu hình Amazon S3
  - Quản lý dữ liệu và quyền truy cập

- **Làm việc với cơ sở dữ liệu RDS**:
  - Tạo cơ sở dữ liệu
  - Quản lý và vận hành RDS

- **Ôn tập và củng cố kiến thức**:
  - Ôn lại IAM, EC2, S3 và RDS
  - Tổng hợp kiến thức từ Tuần 1 và Tuần 2

---

### Tổng quan công việc

| Ngày | Nhiệm vụ                                                                                       | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                  |
| :--: | ---------------------------------------------------------------------------------------------- | :----------: | :-------------: | --------------------------------------------------- |
|  1   | **Định hướng dự án**:<br>- Xây dựng ý tưởng<br>- Lựa chọn dịch vụ AWS<br>- Phác thảo kiến trúc |  19/01/2026  |   19/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  2   | **EC2 & AMI**:<br>- Triển khai EC2<br>- Cấu hình máy ảo<br>- Tạo AMI tùy chỉnh                 |  20/01/2026  |   20/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  3   | **IAM Role & Cloud9**:<br>- Thực hành IAM Role<br>- Làm quen với Cloud9                        |  21/01/2026  |   21/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  4   | **S3 Storage**:<br>- Cấu hình S3<br>- Public access<br>- Versioning                            |  22/01/2026  |   22/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  5   | **RDS & Review**:<br>- Tạo database RDS<br>- Quản lý cơ sở dữ liệu<br>- Ôn tập tổng hợp        |  23/01/2026  |   23/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |

---

### Kết quả đạt được

#### Những gì đã hoàn thành

- Hoàn thiện ý tưởng và kiến trúc ban đầu cho **dự án cuối kỳ**
- Thành thạo hơn trong việc triển khai và quản lý nhiều **EC2 instances**
- Tạo và sử dụng thành công **AMI tùy chỉnh**
- Hiểu và áp dụng **IAM Role** vào các tình huống thực tế
- Làm quen với môi trường phát triển **Cloud9**
- Xây dựng thành công **website tĩnh trên S3**:
  - Public access
  - Versioning
  - Replication (multi-region)
- Tạo và vận hành cơ sở dữ liệu trên **Amazon RDS**
- Củng cố lại kiến thức đã học từ các tuần trước

#### Tóm tắt kiến trúc

- **Compute**: EC2 kết hợp AMI tùy chỉnh
- **Storage**: S3 (Static Website + Versioning + Replication)
- **Database**: RDS (Managed Database)
- **Access Control**: IAM Role
- **Development Environment**: Cloud9
