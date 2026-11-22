# Nginx

## Install
```
dnf install nginx
```

## Edit Config
File: `/etc/nginx/nginx.conf`
```
http{
    server {
        listen <port>;
        listen [::]:<port>;
        server_name _;
        root <Full Path of Document Root>;

        autoindex on;
    }
}
```

## Check config
```
nginx -t
```

## Start Nginx
```
systemctl enable nginx
systemctl start nginx
```

## Other Settings
- firewalld
- SELinux
- Set the document root permission to 711

