---
tags: #linux #www #tip #admin
---

# How can to give write-access of a folder to all users in linux?

From stack exchange - http://superuser.com/questions/19318/how-can-i-give-write-access-of-a-folder-to-all-users-in-linux

To best share with multiple users who should be able to write in `/var/www`, it should be assigned a common group. For example the default group for web content on Ubuntu and Debian is www-data. Make sure all the users who need write access to `/var/www` are in this group.

```bash
sudo usermod -a -G www-data 
```

Then set the correct permissions on /var/www.

```bash
sudo chgrp -R www-data /var/www
sudo chmod -R g+w /var/www
```

Additionally, you should make the directory and all directories below it "set GID", so that all new files and directories created under `/var/www` are owned by the `www-data` group.

```bash
sudo find /var/www -type d -exec chmod 2775 {} ;    
```

Find all files in `/var/www` and add read and write permission for owner and group:

```bash
sudo find /var/www -type f -exec chmod ug+rw {} ;
```

You might have to log out and log back in to be able to make changes if you're editing permission for your own account.