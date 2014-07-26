---
layout: post
title: vagrant server admin bash bash bash bash bash bash bash bash bash bash bash
  bash php bash
categories: []
tags:
- admin
- server
- vagrant
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
<p>#vagrant #server #admin</p>
<p># Vargant Commands</p>
<p>## Add<br />
- Adds a box from the given URL to Vargant and stores it with the provided name.<br />
- Vargant default - http://files.vagrantup.com/precise32.box<br />
- Canonical Vagrant box - http://cloud-images.ubuntu.com/precise/current/precise-server-cloudimg-vagrant-i386-disk1.box</p>
<p>```bash<br />
vagrant box add ubuntu-precise http://cloud-images.ubuntu.com/precise/current/precise-server-cloudimg-vagrant-i386-disk1.box<br />
```</p>
<p>## Box List<br />
- Lists all of the boxes that are installed on the system.</p>
<p>```bash<br />
vagrant bix list<br />
```</p>
<p>## Box Remove<br />
- Removes a box from Vagrant</p>
<p>```bash<br />
vagrant box remove NAME PROVIDER<br />
```</p>
<p>## Init<br />
- Initializes the current directory to be a vagrant environemnt.<br />
- Createres the vagrantfile in the directory if it does not exists.</p>
<p>```bash<br />
vagrant init ubuntu-precise<br />
```</p>
<p>## Suspend<br />
- Stops the machine and saves the state.<br />
- To resume from the same place use `vargant up`</p>
<p>```bash<br />
vagrant suspend<br />
```</p>
<p>## Halt<br />
- Gracefully shuts down the gues operating system.<br />
- Allows for clean boot.</p>
<p>```bash<br />
vagrant halt<br />
```</p>
<p>## Destroy<br />
- Removes all traces of the guest machine, destroys all hard disks and provisioning.</p>
<p>```bash<br />
vagrant destroy<br />
```</p>
<p>## Reload<br />
- Same as running `halt` and `up`.<br />
- Usually required if the vagrantfile was updated.</p>
<p>```bash<br />
vagrant reload<br />
```</p>
<p>## SSH<br />
- SSH into the VM and give access to the shell.</p>
<p>```bash<br />
vagrant ssh<br />
```</p>
<p>## Status<br />
- Tells the state of the VMs that vagrant is managing.</p>
<p>```bash<br />
vagrant status<br />
```</p>
<p>---<br />
# Getting WordPress</p>
<p>```bash<br />
wget http://wordpress.org/latest.tar.gz<br />
tar -xzvf latest.tar.gz<br />
```</p>
<p>```bash<br />
sudo chown www-data:www-data * -R<br />
sudo usermod -a -G www-data username<br />
```</p>
<p>As stated before none of the perm fixes work anymore. You need to change the perms accordingly AND put the following in your wp-config.php:</p>
<p>```php<br />
define('FS_METHOD', 'direct');<br />
```</p>
<p>---</p>
<p># Installing Apache</p>
<p>```bash<br />
apt-get update<br />
apt-get install -y apache2<br />
rm -rf /var/www<br />
ln -fs /vagrant /var/www<br />
```</p>
