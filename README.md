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
- 先安装headscale 首先修改config config.yaml中server_url 为tailscale.{你的主域名} 然后执行 docker-compose up -d
- 后安装headscale-webui 进入目录执行运行 docker-compose up -d
- TOKEN 使用此命令创建apikey `docker exec -it headscale headscale apikey create` 
- 在安装caddy 首先修改etc/Caddy文件 修改cloudflare api token 修改你的主域名 和 {VPS的IP} 替换成你的vps的外网IP
- 打开浏览器 https://www.{你的主域名} 然后输入服务URL为 https://tailscale.{你的主域名} apikey输入上面命令获取的key 进行登录