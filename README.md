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

## Kịch Bản Kiểm Thử 1

### Tên Kịch Bản

Kiểm thử tải cơ bản API lấy danh sách người dùng khi tải thấp

### Mục Đích

Đánh giá hiệu năng API với lượng truy cập thấp

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
| Threads | 20 |
| Ramp-Up | 5 giây |
| Loop Count | 20 |

### Hình Minh Họa
<img width="1920" height="1080" alt="test_plan_1" src="https://github.com/user-attachments/assets/05eecef7-0839-42ee-b8e8-54cdee48095d" />

### Kết Quả 

| Chỉ số | Giá trị |
|---------|----------|
| Tổng Request | 400 |
| Thành công | 400 |
| Thất bại | 0 |
| Tỷ lệ thành công | 100% |
| Average Response Time | 63 ms |

### Trạng Thái

**Thành công**

### Hình Minh Họa
<img width="1920" height="1080" alt="summary_report_1" src="https://github.com/user-attachments/assets/3a05e1a1-7aee-4720-953d-6d750ab4a7ed" />

---

## Kịch Bản Kiểm Thử 2

### Tên Kịch Bản

Kiểm thử tải cơ bản API lấy danh sách người dùng khi tải trung bình

### Mục Đích

Đánh giá hiệu năng API với lượng truy cập vừa

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
| Threads | 100 |
| Ramp-Up | 5 giây |
| Loop Count | 20 |

### Hình Minh Họa
<img width="1920" height="1080" alt="test_plan_2" src="https://github.com/user-attachments/assets/25c5e59b-3052-4b15-ab8f-62f12da9bd7d" />


### Kết Quả 

| Chỉ số | Giá trị |
|---------|----------|
| Tổng Request | 2000 |
| Thành công | 2000 |
| Thất bại | 0 |
| Tỷ lệ thành công | 100% |
| Average Response Time | 66 ms |

### Trạng Thái

**Thành công**

### Hình Minh Họa
<img width="1920" height="1080" alt="summary_report_2" src="https://github.com/user-attachments/assets/8514d2f8-11f8-4e68-b46f-ad2874b373d9" />

---

## Kịch Bản Kiểm Thử 3

### Tên Kịch Bản

Kiểm thử tải cơ bản API lấy danh sách người dùng khi tải cao

### Mục Đích

Đánh giá hiệu năng API với lượng truy cập cao

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
| Threads | 1000 |
| Ramp-Up | 5 giây |
| Loop Count | 20 |

### Hình Minh Họa
<img width="1920" height="1080" alt="test_plan_3" src="https://github.com/user-attachments/assets/7acd65ce-4ee6-4007-80c7-51a9545d8444" />


### Kết Quả 

| Chỉ số | Giá trị |
|---------|----------|
| Tổng Request | 20000 |
| Thành công | 20000 |
| Thất bại | 0 |
| Tỷ lệ thành công | 100% |
| Average Response Time | 98 ms |

### Trạng Thái

**Thành công**

### Hình Minh Họa
<img width="1920" height="1080" alt="summary_report_3" src="https://github.com/user-attachments/assets/cc6f3b26-9a48-451a-938a-ac0e535e6d21" />


---

# 5. Nhận Xét

- API hoạt động ổn định trong các mức tải thử nghiệm.
- Không phát sinh lỗi ngoài dự kiến.
- Response Time duy trì ở mức thấp (<100s).
- Error Rate bằng 0% đối với các endpoint hợp lệ.

---

# 6. Kết Luận

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
