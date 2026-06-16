# BÁO CÁO KIỂM THỬ HIỆU NĂNG API

**Tên Dự Án:** Performance Testing with Apache JMeter

**Ngày Kiểm Thử:** [16/6/2026]

---

# 1. Mục Tiêu Kiểm Thử

Sử dụng Apache JMeter để kiểm thử hiệu năng các API RESTful, đánh giá khả năng phản hồi và xử lý tải của hệ thống khi có nhiều người dùng truy cập đồng thời.

Các mục tiêu chính:

- Đo thời gian phản hồi (Response Time).
- Đánh giá khả năng chịu tải của API.
- Xác định tỷ lệ lỗi khi tải tăng cao.
- Kiểm tra tính ổn định của hệ thống.

---

# 2. Môi Trường Kiểm Thử

| Thành phần | Thông tin |
|------------|-----------|
| Công cụ kiểm thử | Apache JMeter 5.6.3 |
| Java Runtime | Java 24 |
| Hệ điều hành | Windows 10 |
| API kiểm thử | JSONPlaceholder |
| URL gốc | https://jsonplaceholder.typicode.com |

---

# 3. Phương Pháp Kiểm Thử

Kiểm thử được thực hiện bằng Apache JMeter với các thành phần:

- Thread Group
- HTTP Request
- View Results Tree
- Summary Report
- Aggregate Report

Các chỉ số được theo dõi:

- Response Time
- Error Rate
- Throughput
- Number of Samples
- HTTP Response Code

---

# 4. Kịch Bản Kiểm Thử

## Kịch Bản Kiểm Thử

### Tên Kịch Bản

Kiểm thử tải cơ bản API lấy danh sách người dùng

### Mục Đích

Đánh giá hiệu năng API với lượng truy cập thấp.

### Phương Thức HTTP

```http
GET
```

### URL

```http
https://jsonplaceholder.typicode.com/users
```

### Cấu Hình

| Thông số | Giá trị |
|-----------|----------|
| Threads | 10 |
| Ramp-Up | 5 giây |
| Loop Count | 10 |

### Hình Minh Họa
<img width="1920" height="1080" alt="test_plan" src="https://github.com/user-attachments/assets/32ab120f-db01-4fc0-9cfd-945de8268826" />

# 5. Kết Quả
### Kết Quả 

| Chỉ số | Giá trị |
|---------|----------|
| Tổng Request | 100 |
| Thành công | 100 |
| Thất bại | 0 |
| Tỷ lệ thành công | 100% |
| Average Response Time | 179 ms |

### Trạng Thái

**Thành công**

### Hình Minh Họa
<img width="1920" height="1080" alt="summary_report" src="https://github.com/user-attachments/assets/7254dca5-bf26-449a-9988-f3744cf1aa20" />

---

# 6. Nhận Xét

- API hoạt động ổn định trong các mức tải thử nghiệm.
- Không phát sinh lỗi ngoài dự kiến.
- Response Time duy trì ở mức thấp.
- Error Rate bằng 0% đối với các endpoint hợp lệ.
- Hệ thống xử lý đúng khi nhận request không hợp lệ.

---

# 7. Kết Luận

Qua quá trình kiểm thử bằng Apache JMeter:

- Thực hiện thành công kiểm thử tải thấp, tải trung bình và tải cao.
- Đánh giá được thời gian phản hồi của API.
- Kiểm tra được khả năng xử lý đồng thời nhiều request.
- Quan sát và phân tích các báo cáo hiệu năng từ JMeter.
- Nâng cao hiểu biết về quy trình kiểm thử hiệu năng trong thực tế.

---

# Tài Liệu Đính Kèm

## File JMeter

```text
jmeter/Performance_Test.jmx
```

## Thư Mục Hình Ảnh

```text
screenshots/
```
