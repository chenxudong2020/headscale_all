# headscale_all
headscale+headscale_ui+caddy 一键仓库

# 安装步骤
1. 安装git </br>
   debian/ubuntu等</br>
```
apt update && apt install git curl -y
```
   centos等</br>
```
yum update && yum install git curl -y
```
2. 安装docker </br>
   ```
   curl -fsSL https://get.docker.com |bash
   service docker start
   systemctl enable docker
   ```
3. 安装docker-compose </br>
   ```
   curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
   chmod +x /usr/local/bin/docker-compose
   ```
