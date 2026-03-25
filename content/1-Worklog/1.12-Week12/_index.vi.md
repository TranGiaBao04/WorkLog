---
title: "Worklog Tuần 12"
date: 2026-03-30
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu Tuần 12

Trong tuần này, nhóm tập trung đưa hệ thống lên môi trường production, hoàn thiện cơ chế giám sát và chuẩn bị cho giai đoạn vận hành chính thức. Trọng tâm là bảo đảm hệ thống hoạt động ổn định trong môi trường thực tế, có khả năng theo dõi liên tục và sẵn sàng bàn giao.

- **Đưa hệ thống vào production**:
  - Triển khai toàn bộ hệ thống lên môi trường chính thức
  - Cấu hình các dịch vụ cloud và tên miền liên quan
  - Bảo đảm ứng dụng vận hành ổn định sau khi triển khai

- **Thiết lập cơ chế giám sát**:
  - Cài đặt hệ thống monitoring và cảnh báo
  - Theo dõi log cũng như hiệu năng vận hành
  - Xây dựng dashboard để quan sát toàn hệ thống

- **Chuẩn bị cho vận hành chính thức**:
  - Kiểm tra tổng thể lần cuối trước khi đưa vào sử dụng
  - Hoàn thiện tài liệu phục vụ bàn giao
  - Sẵn sàng phục vụ người dùng trong môi trường thực tế

---

### Tổng quan công việc

| Ngày | Công việc                                                                | Ngày bắt đầu | Ngày hoàn thành | Tài liệu                                            |
| :--: | ------------------------------------------------------------------------ | :----------: | :-------------: | --------------------------------------------------- |
|  2   | **Triển khai production**:<br>- Deploy hệ thống<br>- Cấu hình môi trường |  30/03/2026  |   31/03/2026    | [AWS Docs](https://cloudjourney.awsstudygroup.com/) |
|  3   | **Cấu hình dịch vụ**:<br>- Thiết lập domain<br>- Kiểm tra hệ thống       |  01/04/2026  |   02/04/2026    | Nội bộ                                              |
|  4   | **Thiết lập monitoring**:<br>- Cấu hình logging<br>- Thiết lập cảnh báo  |  03/04/2026  |   04/04/2026    | CloudWatch                                          |
|  5   | **Kiểm tra cuối**:<br>- Xác thực hệ thống<br>- UAT                       |  05/04/2026  |   06/04/2026    | Nội bộ                                              |
|  6   | **Chuẩn bị go-live**:<br>- Hoàn thiện tài liệu<br>- Bàn giao vận hành    |  07/04/2026  |   08/04/2026    | Nội bộ                                              |

---

### Thành tựu Tuần 12

#### Những gì đã đạt được

- Triển khai thành công hệ thống lên môi trường **production**
- Thiết lập đầy đủ cơ chế **giám sát và cảnh báo**
- Bảo đảm hệ thống vận hành ổn định trong điều kiện thực tế
- Hoàn tất quá trình kiểm thử cuối và nghiệm thu
- Chuẩn bị xong tài liệu và quy trình bàn giao vận hành
- Hệ thống đã ở trạng thái **sẵn sàng go-live**

#### Tóm tắt kiến trúc

- **Triển khai**: Hạ tầng production cho hệ thống
- **Giám sát**: Log, metrics và alerts
- **Vận hành**: Tài liệu, bàn giao và hỗ trợ khai thác
- **Luồng hệ thống**: User → Production → Monitoring → Admin
- **Giai đoạn**: Production / Chính thức vận hành
