## Setup Nginx

```
sudo apt-get update
sudo apt-get install nginx
sudo mkdir /etc/nginx/ssl
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/nginx/ssl/nginx.key -out /etc/nginx/ssl/nginx.crt
```

sudo /etc/nginx/sites-available/default
```
server {
       listen         80;
       server_name    example.com www.example.com;
       return         301 https://$server_name$request_uri;
}

server {
       listen         443 ssl;
       server_name    example.com www.example.com;
       ssl_certificate /etc/nginx/ssl/nginx.crt;
       ssl_certificate_key /etc/nginx/ssl/nginx.key;

       # add Strict-Transport-Security to prevent man in the middle attacks
       add_header Strict-Transport-Security "max-age=31536000";

  location / {
    root /usr/share/nginx/example;
    index index.html index.htm;
  }
}
```

