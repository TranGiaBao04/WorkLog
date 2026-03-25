---
title: "Worklog Tuần 1"
date: 2026-01-05
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu Tuần 1

Trong tuần đầu tiên, trọng tâm là làm quen với AWS, thiết lập môi trường khởi đầu và xây dựng nền tảng về quản lý tài khoản cũng như kiểm soát chi phí. Các mục tiêu chính gồm:

- **Tìm hiểu tổng quan AWS**:
  - Nắm được cách AWS vận hành và mô hình điện toán đám mây.
  - Tìm hiểu những dịch vụ cốt lõi như EC2, S3, IAM, VPC,...

  - **Làm việc nhóm**:
  - Thành lập nhóm học tập/làm việc.
  - Kết nối, làm quen và trao đổi với các thành viên trong nhóm.

- **Làm quen môi trường lab**:
  - Hiểu cấu trúc của các bài thực hành.
  - Làm quen với quy trình triển khai và thực hiện lab.

- **Thiết lập tài khoản AWS**:
  - Tạo tài khoản AWS theo gói Free Tier.
  - Kích hoạt MFA cho tài khoản Root User.
  - Tạo IAM User với quyền quản trị.
  - Tạo Group và gán quyền Administrator.
  - Làm quen với giao diện AWS Console.

- **Quản lý chi phí với AWS Budgets**:
  - Thiết lập Cost Budget.
  - Thiết lập Usage Budget.
  - Thiết lập Reservation Budget.
  - Thiết lập Savings Plans Budget.
  - Cấu hình các cảnh báo chi phí.
  - Dọn dẹp tài nguyên sau khi sử dụng.

---

### Tổng quan công việc

| Ngày | Nhiệm vụ                                                                                                                          | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                   |
| :--: | --------------------------------------------------------------------------------------------------------------------------------- | :----------: | :-------------: | -------------------------------------------------------------------- | --- |
|  1   | **Tìm hiểu thêm về AWS**:<br>- Hiểu rõ cách hoạt động triển khai của AWS<br>- Tìm hiểu sâu hơn về AWS<br>- Các dịch vụ chính      |  05/01/2026  |   05/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/)                  |
|  2   | **Làm việc nhóm**:<br>- Lập nhóm, làm quen với thành viên trong nhóm<br>- Kết bạn giao lưu<br>- Định hướng học tập                |  06/01/2026  |   06/01/2026    | Nội bộ                                                               |
|  3   | **Làm quen Lab**:<br>- Cấu trúc bài lab<br>- Quy trình thực hành                                                                  |  07/01/2026  |   07/01/2026    | [AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj/) |     |
|  4   | **Thiết lập AWS & IAM**:<br>- Tạo nhóm/quyền Administrator<br>- Bật MFA<br>- Tạo IAM User + Admin Group<br>- Làm quen AWS Console |  08/01/2026  |   08/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/)                  |
|  5   | **AWS Budgets**:<br>- Tạo Cost/Usage/Reservation/Savings Plans Budget<br>- Cấu hình cảnh báo<br>- Dọn dẹp tài nguyên              |  09/01/2026  |   09/01/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/)                  |

---

### Kết quả đạt được

#### Những gì đã hoàn thành

- Hiểu rõ chi tiết hơn về các dịch vụ mà **AWS** cung cấp
- Lập nhóm, kết bạn, giao lưu được với nhiều bạn mới
- Nắm rõ chi tiết, cách triển khai từng **bài lab**
- Tạo thành công tài khoản AWS với **Free Tier (~$100 credit)**
- Bật **MFA cho Root User** để tăng bảo mật
- Tạo **IAM User** riêng để tránh sử dụng Root Account
- Làm quen với **AWS Console**
- Thiết lập ngân sách hàng tháng và cảnh báo chi phí
- Cấu hình **cảnh báo chi phí** và dọn dẹp tài nguyên

#### Tóm tắt nguyên tắc

- **Bảo mật**:
  - Không dùng Root cho daily work
  - Luôn bật MFA

- **Chi phí**:
  - Theo dõi bằng AWS Budgets
  - Alert khi vượt ngưỡng

- **Học tập**:
  - Thực hành lab
  - Làm việc nhóm
