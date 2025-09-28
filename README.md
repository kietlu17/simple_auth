# Simple Auth APIs

## Giới thiệu
Thư mục này gồm hai ví dụ xác thực:
- **Basic Auth**: Xác thực cơ bản qua header Authorization.
- **Cookie Auth**: Xác thực qua cookie và lưu trạng thái đăng nhập.

## Cách test API

### 1. Basic Auth

- **Truy cập public route**
  - GET `/` hoặc `/public`
  - ![public_non_secure.png](public/results/public_non_secure.png)
  - ![public_non_secure_2.png](public/results/public_non_secure_2.png)

- **Truy cập secure route**
  - GET `/secure` với header `Authorization: Basic ...` (username và password lấy từ file .env)
  - Đúng thông tin: ![login_passed.png](public/results/login_passed.png)
  - Sai thông tin: ![login_wrong.png](public/results/login_wrong.png)
  - Không gửi header: ![eror_401.png](public/results/eror_401.png)
  - Sai thông tin: ![eror_403.png](public/results/eror_403.png)

### 2. Cookie Auth

- **Đăng nhập**
  - POST `/login` với thông tin người dùng
  - Thành công: ![cookie.png](public/results/cookie.png), ![mongoDB_cookies.png](public/results/mongoDB_cookies.png)

- **Truy cập profile**
  - GET `/profile`
  - Chưa đăng nhập: ![profile_no_log_in.png](public/results/profile_no_log_in.png)
  - Đã đăng nhập: ![profile_af_login.png](public/results/profile_af_login.png)

- **Đăng xuất**
  - GET `/logout`
  - ![logout.png](public/results/logout.png)

## Khởi chạy
1. Cài đặt package:
   ```bash
   npm install
   ```
2. Tạo file `.env`.
3. Chạy server:
   ```bash
   node basic_auth.js
   ```
   hoặc
   ```bash
   node cookie_auth.js
   ```
4. Test API bằng Postman hoặc curl.

## Hình ảnh minh họa
Các hình ảnh kết quả test API nằm trong thư mục `public/results`.
