### Continous Integration
*On pull request*
1. Checkout repository
2. Setup docker
3. Run unit test, integration test, và others automation test suites

### Continous Deployment/Delivery
*On push*
1. Checkout repository
2. Tạo file .env bằng github secret
3. setup docker
4. login to registry
5. build image and push to registry
    build image với tag được định nghĩa trong .env file, file .env lại được tạo bởi deploy flow.
6. connect to vm, copy docker-compose và .env, pull image:latest and run docker compose


_Thông thường, CI có thể sử dụng github actions_
_Hiện nay, Việc CD thường sẽ do do phía hosting cung cấp. phía host sẽ lắng nghe các thay đổi từ source code hoặc image registry, sau đó sẽ pull các thay đổi về và triển khai một cách riêng tư_

_Trong trường hợp cần độ tin cậy cao, người ta thường deploy lên môi trường testing sau đó qua kiểm thử toàn diện thì mới deploy lên production_