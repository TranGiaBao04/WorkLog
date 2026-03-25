---
title: "Worklog Tuần 9"
date: 2026-03-09
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu Tuần 9

Trong tuần này, nhóm tập trung đưa dự án vào giai đoạn chạy thử trên môi trường triển khai, đồng thời kiểm tra toàn diện các thành phần của hệ thống và xử lý những vấn đề phát sinh trong quá trình test. Mục tiêu chính là bảo đảm ứng dụng hoạt động ổn định trước khi bước sang giai đoạn demo hoặc phát hành.

- **Triển khai hệ thống lên môi trường chạy thử**:
  - Đưa ứng dụng lên EC2 để kiểm tra trong điều kiện gần với thực tế
  - Thiết lập và đồng bộ các dịch vụ liên quan như RDS, S3 và Map
  - Xác minh khả năng giao tiếp giữa các thành phần trong hệ thống

- **Kiểm thử toàn bộ hệ thống**:
  - Chạy thử các chức năng quan trọng của ứng dụng
  - Rà soát giao diện và trải nghiệm sử dụng
  - Kiểm tra sự đồng nhất dữ liệu giữa frontend và backend

- **Khắc phục lỗi và tinh chỉnh**:
  - Phát hiện và sửa các lỗi xuất hiện trong quá trình kiểm thử
  - Nâng cao hiệu năng cũng như tính ổn định của ứng dụng

- **Hoàn thiện trước giai đoạn trình bày**:
  - Đảm bảo hệ thống vận hành trơn tru
  - Chuẩn bị cho demo hoặc giai đoạn phát hành tiếp theo

---

### Tổng quan công việc

| Ngày | Nhiệm vụ                                                                             | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                  |
| :--: | ------------------------------------------------------------------------------------ | :----------: | :-------------: | --------------------------------------------------- |
|  1   | **Thiết lập triển khai**:<br>- Deploy ứng dụng lên EC2<br>- Cấu hình môi trường chạy |  09/03/2026  |   09/03/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  2   | **Kiểm thử hệ thống**:<br>- Test các chức năng chính<br>- Kiểm tra luồng dữ liệu     |  10/03/2026  |   10/03/2026    | Internal                                            |
|  3   | **Sửa lỗi**:<br>- Phát hiện và khắc phục bug<br>- Debug hệ thống                     |  11/03/2026  |   11/03/2026    | Internal                                            |
|  4   | **Tối ưu hệ thống**:<br>- Tối ưu code<br>- Cải thiện hiệu năng                       |  12/03/2026  |   12/03/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  5   | **Kiểm thử cuối**:<br>- Rà soát toàn bộ hệ thống<br>- Chuẩn bị demo                  |  13/03/2026  |   13/03/2026    | Internal                                            |

---

### Kết quả đạt được

#### Những gì đã hoàn thành

- Triển khai thành công hệ thống thử nghiệm trên **Amazon EC2**
- Thiết lập kết nối ổn định với các dịch vụ:
  - **Amazon RDS**
  - **Amazon S3**
  - **AWS Map**
- Kiểm tra được đầy đủ các luồng chức năng chính của ứng dụng
- Phát hiện và xử lý các lỗi xuất hiện trong quá trình kiểm thử
- Cải thiện hiệu năng vận hành và trải nghiệm người dùng
- Hoàn thiện hệ thống ở mức **đủ điều kiện để demo**

#### Tóm tắt kiến trúc

- **Compute**: EC2 dùng để triển khai và chạy ứng dụng
- **Database**: RDS (SQL Server) phục vụ lưu trữ dữ liệu
- **Storage**: S3 dùng cho file tĩnh
- **Map**: AWS Map phục vụ chức năng vị trí
- **Flow**: Frontend → Backend → AWS Services
- **Stage**: Testing / Pre-production
