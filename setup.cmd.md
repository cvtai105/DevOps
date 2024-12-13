### Kết nối tới azure virtual machine trên window
```bash
ssh -i ~/.ssh/keypaire.rsa.vm1.pem azureuser@20.6.107.157
```
- File ~/.ssh/keypaire.rsa.vm1.pem là rsa private key được cấp khi tạo machine, có thể tạo mới trên azure portal

### Cập nhật hệ thống
```bash
sudo apt update && sudo apt upgrade -y
```

### Cài docker
```bash
sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker $USER
```

### Kiểm tra docker
```bash
docker --version
```

### Cài docker compose

### Tạo file docker-compose

### Run docker-compose
