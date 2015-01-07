---
tags: #vagrant #server #admin
---

# Vargant Commands

## Add
- Adds a box from the given URL to Vargant and stores it with the provided name.
- Vargant default - http://files.vagrantup.com/precise32.box
- Canonical Vagrant box - http://cloud-images.ubuntu.com/precise/current/precise-server-cloudimg-vagrant-i386-disk1.box

```bash
vagrant box add ubuntu-precise http://cloud-images.ubuntu.com/precise/current/precise-server-cloudimg-vagrant-i386-disk1.box
```

## Box List
- Lists all of the boxes that are installed on the system.

```bash
vagrant bix list
```

## Box Remove
- Removes a box from Vagrant

```bash
vagrant box remove NAME PROVIDER
```

## Init
- Initializes the current directory to be a vagrant environemnt.
- Createres the vagrantfile in the directory if it does not exists.

```bash
vagrant init ubuntu-precise
```

## Suspend
- Stops the machine and saves the state.
- To resume from the same place use `vargant up`

```bash
vagrant suspend
```

## Halt
- Gracefully shuts down the gues operating system.
- Allows for clean boot.

```bash
vagrant halt
```

## Destroy
- Removes all traces of the guest machine, destroys all hard disks and provisioning.

```bash
vagrant destroy
```

## Reload
- Same as running `halt` and `up`.
- Usually required if the vagrantfile was updated.

```bash
vagrant reload
```

## SSH
- SSH into the VM and give access to the shell.

```bash
vagrant ssh
```

## Status
- Tells the state of the VMs that vagrant is managing.

```bash
vagrant status
```

---
# Getting WordPress

```bash
wget http://wordpress.org/latest.tar.gz
tar -xzvf latest.tar.gz 
```

```bash
sudo chown www-data:www-data * -R 
sudo usermod -a -G www-data username
```

As stated before none of the perm fixes work anymore. You need to change the perms accordingly AND put the following in your wp-config.php:

```php
define('FS_METHOD', 'direct');
```

---

# Installing Apache

```bash
apt-get update
apt-get install -y apache2
rm -rf /var/www
ln -fs /vagrant /var/www
```