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
[api-domain-com].conf
[portal-domain-com].conf
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
upstream api_domain_com_upstream { # exact domain naming convention
    server 127.0.0.1:1000; # local ip & port of APP inside of virtual machine
    keepalive 64;
}

server {
    listen 80;

    server_name 192.0.2.1;
    server_name api.domain.com;

    client_max_body_size 100M; # use for APIs and backends, remove if static HTML

    add_header 'Content-Security-Policy' 'upgrade-insecure-requests';
   
    location / {
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header Host $http_host;
        
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        
        proxy_pass http://api_domain_com_upstream;
        proxy_redirect off;
        proxy_read_timeout 240s;
    }
}

server {
    listen 443 ssl http2;

    server_name 192.0.2.1;
    server_name api.domain.com;

    ssl_certificate     /path/to/domain-certificate.crt; # or fullchain.pem
    ssl_certificate_key /path/to/domain-key.key; # or private-key.pem

    client_max_body_size 100M; # use for APIs and backends, remove if static HTML

    add_header 'Content-Security-Policy' 'upgrade-insecure-requests';
   
    location / {
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header Host $http_host;
        
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        
        proxy_pass http://api_domain_com_upstream;
        proxy_redirect off;
        proxy_read_timeout 240s;
    }
}
```

```
upstream portal_domain_com_upstream { # exact domain naming convention
    server 127.0.0.1:1000; # local ip & port of APP inside of virtual machine
    keepalive 64;
}

server {
    listen 80;

    server_name 192.0.2.1;
    server_name portal.domain.com;

    add_header 'Content-Security-Policy' 'upgrade-insecure-requests';
   
    location / {
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header Host $http_host;
        
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        
        proxy_pass http://portal_domain_com_upstream;
        proxy_redirect off;
        proxy_read_timeout 240s;
    }
}

server {
    listen 443 ssl http2;

    server_name 192.0.2.1;
    server_name portal.domain.com;

    ssl_certificate     /path/to/domain-certificate.crt; # or fullchain.pem
    ssl_certificate_key /path/to/domain-key.key; # or private-key.pem

    add_header 'Content-Security-Policy' 'upgrade-insecure-requests';
   
    location / {
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header Host $http_host;
        
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        
        proxy_pass http://portal_domain_com_upstream;
        proxy_redirect off;
        proxy_read_timeout 240s;
    }
}
```
