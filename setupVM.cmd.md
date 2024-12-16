### Tạo virtual machine bằng azure portal

### Kết nối tới azure virtual machine trên window
```bash
ssh -i ~/.ssh/keypaire.rsa.vm1.pem azureuser@20.6.107.157
```
```bash
ssh -i ~/.ssh/vm2_key.pem azureuser@20.198.223.165
```
- File ~/.ssh/keypaire.rsa.vm1.pem là rsa private key được cấp khi tạo machine, có thể tạo mới trên azure portal. cần copy file .pem đc cấp vào ~/.ssh/ 

### Cập nhật hệ thống
```bash
sudo apt update && sudo apt upgrade -y
```

### Cài docker và docker-compose
Sử dung apt để install docker và docker-compose: https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository

Sau khi install, Cần start docker
```bash
sudo systemctl start docker
sudo systemctl enable docker    #start docker on boot
```
Thêm docker vào user group, khi sử dụng không cần gọi sudo(superuser do)
```bash
sudo usermod -aG docker $USER
newgrp - docker     #Switch session to docker group
```

### Kiểm tra docker
```bash
docker --version
docker compose version
```

### Cài NGinx và https

### Tạo và copy file docker-compose và .env
```bash
mkdir solutionName
cd solutionName
touch docker-compose.yml
nano docker-compose.yml
```

Tương tự với file .env.
_nếu docker-compose và .env thay đổi nhiều thì nên tích hợp vào cicd_


### Run docker-compose
```bash
docker compose up -d
```

câu lệnh này sẽ pull images nếu chưa có và chạy images
