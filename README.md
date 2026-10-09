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
- Cấu hình Request:
  + Phương thức: GET
  + Endpoint: https://jsonplaceholder.typicode.com/posts
  + Query Parameters: userId = 1 (yêu cầu máy chủ chỉ lọc và trả về danh sách các bài viết thuộc tác giả có userId = 1)
  + URL hoàn chỉnh: https://jsonplaceholder.typicode.com/posts?userId=1
- Kết quả thực thi:
  + Status Code: 200 OK (yêu cầu thành công, máy chủ phản hồi đúng tài nguyên).
  + Thời gian phản hồi (Response Time): 61 ms (tốc độ xử lý nhanh, mạng ổn định).
  + Dung lượng phản hồi: 1.86 KB.
  + Response Payload: Mảng JSON gồm 10 phần tử bài viết. Mỗi đối tượng bài viết có cấu trúc chuẩn gồm 4 trường dữ liệu: userId, id, title, và body.
  + Kết quả trả về:
    ```Kết quả
    {
        "userId": 1,
        "id": 1,
        "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
        "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
    },
    {
        "userId": 1,
        "id": 2,
        "title": "qui est esse",
        "body": "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla"
    },
    {
        "userId": 1,
        "id": 3,
        "title": "ea molestias quasi exercitationem repellat qui ipsa sit aut",
        "body": "et iusto sed quo iure\nvoluptatem occaecati omnis eligendi aut ad\nvoluptatem doloribus vel accusantium quis pariatur\nmolestiae porro eius odio et labore et velit aut"
    },
    {
        "userId": 1,
        "id": 4,
        "title": "eum et est occaecati",
        "body": "ullam et saepe reiciendis voluptatem adipisci\nsit amet autem assumenda provident rerum culpa\nquis hic commodi nesciunt rem tenetur doloremque ipsam iure\nquis sunt voluptatem rerum illo velit"
    },
    {
        "userId": 1,
        "id": 5,
        "title": "nesciunt quas odio",
        "body": "repudiandae veniam quaerat sunt sed\nalias aut fugiat sit autem sed est\nvoluptatem omnis possimus esse voluptatibus quis\nest aut tenetur dolor neque"
    },
    {
        "userId": 1,
        "id": 6,
        "title": "dolorem eum magni eos aperiam quia",
        "body": "ut aspernatur corporis harum nihil quis provident sequi\nmollitia nobis aliquid molestiae\nperspiciatis et ea nemo ab reprehenderit accusantium quas\nvoluptate dolores velit et doloremque molestiae"
    },
    {
        "userId": 1,
        "id": 7,
        "title": "magnam facilis autem",
        "body": "dolore placeat quibusdam ea quo vitae\nmagni quis enim qui quis quo nemo aut saepe\nquidem repellat excepturi ut quia\nsunt ut sequi eos ea sed quas"
    },
    {
        "userId": 1,
        "id": 8,
        "title": "dolorem dolore est ipsam",
        "body": "dignissimos aperiam dolorem qui eum\nfacilis quibusdam animi sint suscipit qui sint possimus cum\nquaerat magni maiores excepturi\nipsam ut commodi dolor voluptatum modi aut vitae"
    },
    {
        "userId": 1,
        "id": 9,
        "title": "nesciunt iure omnis dolorem tempora et accusantium",
        "body": "consectetur animi nesciunt iure dolore\nenim quia ad\nveniam autem ut quam aut nobis\net est aut quod aut provident voluptas autem voluptas"
    },
    {
        "userId": 1,
        "id": 10,
        "title": "optio molestias id quia eum",
        "body": "quo et expedita modi cum officia vel magni\ndoloribus qui repudiandae\nvero nisi sit\nquos veniam quod sed accusamus veritatis error"
    }
<img width="1227" height="902" alt="image" src="https://github.com/user-attachments/assets/281d8780-ed94-4b8b-92b6-8d24ae2b6f90" />


### 3.2. POST Request
- Mục tiêu: Kiểm tra khả năng tạo mới một bản ghi tài nguyên bằng phương thức gửi kèm dữ liệu cấu trúc JSON trong Request Body lên máy chủ.
- Cấu hình Request:
  + Phương thức (HTTP Method): POST
  + Endpoint: [https://jsonplaceholder.typicode.com/posts](https://jsonplaceholder.typicode.com/posts)
  + Headers: Content-Type: application/json
  + Request Body (raw JSON):
    ```JSON
    JSON
    {
      "title": "Báo cáo Lab 7 - Kiểm thử API",
      "body": "Sinh viên: Phạm Tiến Chiêu - MSSV: 23010526",
      "userId": 1
    }
- Kết quả thực thi:
  + Mã trạng thái (Status Code): 201 Created (xác nhận tài nguyên mới đã được khởi tạo thành công trên hệ thống)
  + Thời gian phản hồi (Response Time): 903 ms
  + Dung lượng phản hồi: 1.14 KB
  + Dữ liệu phản hồi (Response Body): Máy chủ tiếp nhận thành công và trả về đối tượng JSON gồm đầy đủ thông tin vừa gửi cùng trường id: 101 tự sinh:
    ```JSON
    JSON
    {
      "title": "Báo cáo Lab 7 - Kiểm thử API",
      "body": "Sinh viên: Phạm Tiến Chiêu - MSSV: 23010526",
      "userId": 1,
      "id": 101
    }
<img width="1227" height="897" alt="image" src="https://github.com/user-attachments/assets/bbeab2f0-49fb-4e5e-a684-92c05c35db6e" />


### 3.3. Kiểm thử tự động (Tests tab)
- Mục tiêu: Tự động hóa quá trình xác minh phản hồi từ máy chủ bằng cách thiết lập các câu lệnh kiểm tra (Assertions) với thư viện pm.test() và pm.expect() trong tab Scripts (After response).
- Kịch bản kiểm thử (Test Scripts):
  + Kiểm tra Status Code trả về đúng chuẩn 201 Created
    ```javascript
    pm.test("Status code is 201 Created", function () {
        pm.response.to.have.status(201);
    });
  + Kiểm tra thời gian phản hồi (Response Time) đạt yêu cầu (< 1500ms)
    ```javascript
    pm.test("Response time is acceptable (under 1500ms)", function () {
        pm.expect(pm.response.responseTime).to.be.below(1500);
    });
  + Kiểm tra định dạng Header Content-Type trả về là application/json
    ```javascript
    pm.test("Content-Type header is JSON", function () {
        pm.expect(pm.response.headers.get("Content-Type")).to.include("application/json");
    });
  + Kiểm tra ID tự sinh là 101 và tiêu đề bài viết khớp với dữ liệu gửi đi
    ```javascript
    pm.test("Response contains generated id 101 and correct title", function () {
        const jsonData = pm.response.json();
        pm.expect(jsonData).to.have.property("id");
        pm.expect(jsonData.id).to.eql(101);
        pm.expect(jsonData.title).to.eql("Báo cáo Lab 7 - Kiểm thử API");
    });
- Kết quả thực thi (Test Results):
  + Trạng thái: PASS (4/4) (100% ca kiểm thử đều vượt qua).
  + Đánh giá chi tiết:
    PASS: Status code is 201 Created: Máy chủ phản hồi mã xác nhận tài nguyên đã được tạo thành công.
    PASS: Response time is acceptable (under 1500ms): Thời gian đáp ứng của API nằm trong ngưỡng hiệu năng cho phép.
    PASS: Content-Type header is JSON: Dữ liệu trả về đúng định dạng JSON chuẩn.
    PASS: Response contains generated id 101 and correct title: Dữ liệu phản hồi toàn vẹn, bảo toàn đúng title gửi lên và tự động sinh mã định danh id: 101.
<img width="1227" height="896" alt="image" src="https://github.com/user-attachments/assets/3e3adae7-72f0-4a7d-8dee-745f12e3156d" />

