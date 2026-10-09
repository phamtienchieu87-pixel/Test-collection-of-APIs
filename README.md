# Báo Cáo Lab 7: Kiểm Thử API Bằng Postman

## 1. Thông tin sinh viên
- Họ và tên: Phạm Tiến Chiêu
- Mã sinh viên: 23010526

## 2. Tổng quan về Postman
Postman là nền tảng API Client hàng đầu hiện nay, hỗ trợ lập trình viên và kiểm thử viên trong việc xây dựng, kiểm thử, tài liệu hóa và giám sát các dịch vụ Web API. Công cụ hỗ trợ đầy đủ các phương thức HTTP chuẩn (GET, POST, PUT, PATCH, DELETE,...), cho phép cấu hình linh hoạt Headers, Query Parameters, Authentication và Request Body.
- Ngoài khả năng lưu trữ lịch sử gọi request và tổ chức theo Collections, Postman còn tích hợp môi trường thực thi JavaScript mạnh mẽ (Sandbox) tại hai giai đoạn:
- Pre-request Script: Thiết lập dữ liệu giả lập, mã hóa dữ liệu hoặc tính toán biến môi trường trước khi gửi request.
- Post-response (Tests Script): Viết các câu lệnh assertions kiểm tra tự động cấu trúc dữ liệu, mã phản hồi (Status Code), thời gian đáp ứng (Response Time) và dữ liệu nghiệp vụ sau khi nhận phản hồi.

## 3. Kết quả thực hiện
### 3.1. GET Request
- Mục tiêu: Kiểm tra khả năng truy xuất danh sách dữ liệu game trực tuyến theo tiêu chí lọc từ public API.
- 
- <img width="1227" height="887" alt="image" src="https://github.com/user-attachments/assets/1572be86-227c-4a94-a46b-bec2615d50a9" />


### 3.2. POST Request
- Mô tả API đã test & Body gửi đi.
- ![Mô tả ảnh](./images/post-request.png)

### 3.3. Kiểm thử tự động (Tests tab)
- Kết quả chạy test script (Status code 200, Response time,...).
- ![Mô tả ảnh](./images/test-result.png)
