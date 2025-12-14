# Nginx

1. Installation setup: 

```sh
    sudo apt-get update
    sudo apt install nginx -y
```
2. check status

```sh
    systemctl status nginx
```
3. Add rule: 
```sh
events{}
http {
    server {
        auth_basic "Restricted Access";
        auth_basic_user_file /etc/nginx/.htpasswd;
        listen 9000;
        root /project/html;
        location / {
            try_files /process.html =404;
        }
        location /info {
        try_files /info.html =404;
        }
    }
}

```
4. install httpasswd
```sh
    apt install apache2-utils -y
    which htpasswd

```
5. create a user and password: 
```sh
    htpasswd -c /etc/nginx/.htpasswd <user-name>
```
6. restart or reload nginx
```sh
    systemctl restart nginx
```