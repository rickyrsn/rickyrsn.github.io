---
layout: post
title:  "Installing Apache, PHP-FPM, Phalcon, IonCube on Ubuntu 16.04"
date:   2019-02-02 13:29:36 +0700
---

# Installing Apache2
```s
sudo apt-get update
sudo apt-get install apache2
```

# Installing PHP-FPM
```s
sudo add-apt-repository ppa:ondrej/php
sudo apt-get update
sudo apt-get install php7.1 php7.1-fpm

# Instal Phalcon and Ioncube Loader Module
> curl -s https://packagecloud.io/install/repositories/phalcon/stable/script.deb.sh | sudo bash

> sudo apt-get update

> sudo apt-get install php7.1-phalcon

> sudo apt-get install -y gcc make re2c libpcre3-dev php7.1-dev build-essential php7.1-zip

> sudo nano /etc/php/7.1/fpm/conf.d/01-phalcon.ini

Add this following line
> extension=phalcon.so

> cd /tmp
> wget https://downloads.ioncube.com/loader_downloads/ioncube_loaders_lin_x86-64.tar.gz
> tar xvfz ioncube_loaders_lin_x86-64.tar.gz
> sudo cp ioncube/ioncube_loader_lin_7.1.so /(your extension_dir)/
> sudo nano /etc/php/7.1/fpm/conf.d/00-ioncube.ini
> 
Add the following line to 00-ioncube.ini
> zend_extension = /(your extension_dir)/ioncube_loader_lin_7.1.so
> 
# Restart Service
```shell
sudo service apache2 restart
sudo service php7.1-fpm restart
```

# Apache Configuration
```shell
sudo a2enmod actions fastcgi alias proxy_fcgi
udo nano /etc/apache2/sites-available/000-default.conf
```

Update the configuration as followings.

<VirtualHost *:80>
    ServerName example.com
    ServerAlias www.example.com
    DocumentRoot /var/www/html
    <Directory /var/www/html>
        Options -Indexes +FollowSymLinks +MultiViews
        AllowOverride All
        Require all granted
    </Directory>
    <FilesMatch \.php$>
        #2.4.10+ can proxy to unix socket
        SetHandler "proxy:unix:/var/run/php/php7.2-fpm.sock|fcgi://localhost/"
 		#Else we can just use a tcp socket:
        #SetHandler "proxy:fcgi://127.0.0.1:9000"
    </FilesMatch>
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

Save changes configuration file and restart Apache
> sudo a2enmod rewrite
> sudo systemctl restart apache2
> 