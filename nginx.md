# Nginx #

## Installation ##
```
sudo apt-get update
sudo apt-get install nginx
sudo nginx -v
```

## Sample Config File and Commands  ##
sample naming convention
```
[app-name-api].conf
[app-name-ws].conf
```
with environment
```
[app-name-api-dev].conf
[app-name-api-stage].conf
[app-name-api-prod].conf
```
Common Commands
```
sudo systemctl status nginx
sudo systemctl stop nginx
sudo systemctl start nginx
sudo systemctl reload nginx
```

## SSL Setup ##
```
sudo mkdir -p /etc/nginx/ssl
cd /etc/nginx/ssl
```

```
sudo openssl req -x509 -nodes -days 365 \
  -newkey rsa:2048 \
  -keyout app-name-api-dev.key \
  -out app-name-api-dev.crt \
  -subj "/CN=app-name-api-dev"
```

```
upstream app_name_api_dev_upstream { # app_name or name of project
    server 127.0.0.1:1000; # local ip & port of APP inside of virtual machine
    keepalive 64;
}

server {
    listen 443 ssl http2;

    server_name 192.0.2.1; # public ip (URL)

    ssl_certificate     /path/to/app-name-api-dev.crt;
    ssl_certificate_key /path/to/app-name-api-dev.key;

    client_max_body_size 100M; # use for APIs and backends, remove if static HTML

    add_header 'Content-Security-Policy' 'upgrade-insecure-requests';
   
    location / {
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header Host $http_host;
        
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        
        proxy_pass http://app_name_api_dev_upstream;
        proxy_redirect off;
        proxy_read_timeout 240s;
    }
}
```
