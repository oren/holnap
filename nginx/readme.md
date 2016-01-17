## Setup Nginx

on my laptop

```
sudo apt-get update
sudo apt-get install nginx
sudo mkdir /etc/nginx/ssl
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/nginx/ssl/nginx.key -out /etc/nginx/ssl/nginx.crt
```

sudo vim /etc/hosts

```
127.0.0.1 example.com
127.0.0.1 www.example.com
127.0.0.1 api.example.com
```
