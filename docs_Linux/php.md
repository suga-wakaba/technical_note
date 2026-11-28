# PHP

## Install PHP and Start FPM
```
dnf install php
dnf install php-cli
dnf install php-fpm
dnf install php-pgsql
systemctl elable php-fpm
systemctl start php-fpm
```

## Edit Nginx Conf
Add the code below inside the `server{}` block in `nginx.conf`
```
        location / {
            try_files $uri $uri/ =404;
        }

        location ~ \.php$ {
            try_files $uri =404;
            include fastcgi_params;
            fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
            fastcgi_pass unix:/run/php-fpm/www.sock;
        }
```

