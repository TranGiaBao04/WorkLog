---
title: "Worklog Tuần 8"
date: 2026-03-02
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu Tuần 8

Trong tuần này, nhóm chính thức bước vào giai đoạn hiện thực hóa dự án bằng việc phát triển các thành phần đầu tiên của hệ thống và đưa các dịch vụ AWS cần thiết vào quy trình vận hành. Trọng tâm không chỉ nằm ở việc viết mã nguồn mà còn ở quá trình kết nối các lớp của ứng dụng để tạo nên một luồng hoạt động hoàn chỉnh.

- **Triển khai dự án ở mức thực tế**:
  - Bắt đầu xây dựng các chức năng cốt lõi của hệ thống
  - Liên kết frontend, backend và database thành một kiến trúc thống nhất
  - Hoàn thiện phần khung kỹ thuật ban đầu để làm nền cho các giai đoạn tiếp theo

- **Đưa các dịch vụ AWS vào hệ thống**:
  - Sử dụng **Amazon EC2** làm môi trường chạy ứng dụng
  - Tích hợp **Amazon RDS** để quản lý dữ liệu quan hệ
  - Dùng **Amazon S3** cho việc lưu trữ file tĩnh và dữ liệu người dùng
  - Ứng dụng **AWS Map** để hỗ trợ hiển thị bản đồ và thông tin vị trí

- **Kiểm thử và điều chỉnh hệ thống**:
  - Kiểm tra sự phối hợp giữa các thành phần sau khi tích hợp
  - Xử lý các lỗi phát sinh trong quá trình phát triển
  - Sắp xếp lại cấu trúc dự án để thuận lợi hơn cho việc mở rộng sau này

---

### Tổng quan công việc

| Ngày | Nhiệm vụ                                                                                                      | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                  |
| :--: | ------------------------------------------------------------------------------------------------------------- | :----------: | :-------------: | --------------------------------------------------- |
|  1   | **Khởi tạo phần phát triển dự án**:<br>- Thiết lập cấu trúc project<br>- Bắt đầu xây dựng các chức năng chính |  02/03/2026  |   02/03/2026    | Internal                                            |
|  2   | **Tích hợp backend và cơ sở dữ liệu**:<br>- Kết nối backend với RDS<br>- Xử lý các thao tác dữ liệu cơ bản    |  03/03/2026  |   03/03/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  3   | **Tích hợp S3**:<br>- Thiết lập S3<br>- Upload và quản lý tài nguyên tĩnh                                     |  04/03/2026  |   04/03/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  4   | **Tích hợp dịch vụ bản đồ**:<br>- Kết nối AWS Map<br>- Hiển thị dữ liệu vị trí trên giao diện                 |  05/03/2026  |   05/03/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  5   | **Triển khai EC2 và kiểm thử**:<br>- Deploy ứng dụng lên EC2<br>- Kiểm thử luồng tích hợp toàn hệ thống       |  06/03/2026  |   06/03/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |

---

### Kết quả đạt được

#### Những gì đã hoàn thành

- Bắt đầu chuyển dự án từ giai đoạn ý tưởng sang **giai đoạn phát triển thực tế**
- Xây dựng được phần khung kết nối giữa **frontend, backend và database**
- Tích hợp thành công **Amazon RDS** để phục vụ lưu trữ dữ liệu
- Thiết lập và sử dụng **Amazon S3** cho tài nguyên tĩnh của hệ thống
- Kết nối **AWS Map** để hỗ trợ chức năng hiển thị vị trí
- Thử nghiệm triển khai ứng dụng trên **Amazon EC2**
- Kiểm tra được luồng hoạt động cơ bản của toàn hệ thống sau khi tích hợp

#### Tóm tắt kiến trúc

- **Compute**: Amazon EC2 đóng vai trò môi trường chạy ứng dụng
- **Database**: Amazon RDS lưu trữ dữ liệu quan hệ của hệ thống
- **Storage**: Amazon S3 phục vụ lưu file và tài nguyên tĩnh
- **Map Service**: AWS Map hỗ trợ hiển thị bản đồ và dữ liệu vị trí
- **Application Flow**: Frontend ↔ Backend ↔ AWS Services
