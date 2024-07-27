# NGINX #
sudo apt-get update
sudo apt-get install nginx
sudo nginx -v
## Installation ##

## Sample Config File and Commans##
[app-name-api].conf
[app-name-ws].conf
```
sudo systemctl status nginx
sudo systemctl stop nginx
sudo systemctl start nginx
sudo systemctl reload nginx
```

```
upstream app_name_upstream {
    server 127.0.0.1:1000;
    keepalive 64;
}

server {
    listen 1000 ssl;

    server_name 127.0.0.1;

    ssl_certificate_key /path/to/MyKey.key;
    ssl_certificate     /path/to/MyCertificate.crt;

    add_header 'Content-Security-Policy' 'upgrade-insecure-requests';
   
    location / {
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header Host $http_host;
        
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        
        proxy_pass http://app_name_upstream/;
        proxy_redirect off;
        proxy_read_timeout 240s;
    }
}
```
