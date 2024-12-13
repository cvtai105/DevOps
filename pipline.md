# Quy trình chuẩn cho việc triển khai ứng dụng nhỏ với docker
### 1. Triển khai lần đầu với Virtual machine
- Run test.
- Build và push images lên container registry
- Tự tạo server hoặc Mua virtual machine trên các nền tảng hosting như Azure, TenTen, AWS.
- Cài đặt cấu hình, cho phép kết nối, điều khiển từ xa.
- Kết nối tới VM và cài docker engine, docker compose
- Cài đặt nginx, https.
- Copy files không được định nghĩa trong image như .env file, docker-compose file.
- Run docker compose (tự động pull image)

### 2. Triển khai những lần tiếp theo
- Test 
- Build, Push image lên container registry
- Pull image và chạy docker compose.

# Tại sao không pull code, test, build và triển khai ngay trên máy chủ?
- Test, build tốn thời gian và tài nguyên, ảnh hưởng tới tính availability của ứng dụng
- Source code cần bảo mật
- Có thể quản lý phiên bản trên registry, giúp dễ dàng rollback nếu có lỗi xảy ra

### Với các ứng dụng lớn nên xem xét sử dụng k8s