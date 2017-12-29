# basic configuration for index.php

## install nginx

## install php php-fpm php-mysql

## change configuration /etc/nginx/sites-available/default  this is in ubuntu

```conf
server {
        ....
        location ~.php$ {
                root html;
                <font color="red">fastcgi_pass unix:/var/run/php/php7.1-fpm.sock;</font>
                fastcgi_index index.php;
                fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
                include fastcgi_params;
        }
        ...
}
```

> note 
> <font color="red">fastcgi_pass unix:/var/run/php/php7.1-fpm.sock;</font> 
> should be the right unix when check the socket under path /var/run