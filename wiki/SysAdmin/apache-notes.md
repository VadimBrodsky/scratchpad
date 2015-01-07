---
tags: #server #admin #apache
---

# Apache Notes

## To Restart Apache

- Install LAMP - https://www.digitalocean.com/community/articles/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu

```bash
sudo service apache2 restart
```

## Set Apache User
Add to the following file - `/etc/apache2/httpd.conf `

```bash
User vagrant
Group vagrant
```

## Allow WordPress Permalint Rewrite
- Enable Mod Rewrite
- Change `AllowOverride None` to `AllowOverride All`
- Restart Apache

```bash
sudo a2enmod rewrite
sudo nano /etc/apache2/sites-enabled/000-default
sudo /etc/init.d/apache2 restart
```