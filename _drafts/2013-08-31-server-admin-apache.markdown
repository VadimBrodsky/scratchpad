---
layout: post
title: server admin apache bash bash bash
categories: []
tags:
- admin
- apache
- server
status: publish
type: post
published: true
meta:
  _pingme: '1'
  _encloseme: '1'
author:
  login: vadimbrodsky
  email: vadim@vadimbrodsky.com
  display_name: Vadim
  first_name: Vadim
  last_name: Brodsky
---
<p>#server #admin #apache</p>
<p># Apache Notes</p>
<p>## To Restart Apache</p>
<p>- Install LAMP - https://www.digitalocean.com/community/articles/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu</p>
<p>```bash<br />
sudo service apache2 restart<br />
```</p>
<p>## Set Apache User<br />
Add to the following file - `/etc/apache2/httpd.conf `</p>
<p>```bash<br />
User vagrant<br />
Group vagrant<br />
```</p>
<p>## Allow WordPress Permalint Rewrite<br />
- Enable Mod Rewrite<br />
- Change `AllowOverride None` to `AllowOverride All`<br />
- Restart Apache</p>
<p>```bash<br />
sudo a2enmod rewrite<br />
sudo nano /etc/apache2/sites-enabled/000-default<br />
sudo /etc/init.d/apache2 restart<br />
```</p>
