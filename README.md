
Warmup
======

IDE Installation &amp; Environment Setup Documents

### Installation Apache & Php & MySQL

<a href="https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu-14-04">https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu-14-04</a>

### Enable Apache2 Mode Rewrite (.htaccess)

```php
sudo a2enmod rewrite
```

Go

```php
vim /etc/apache2/apache2.conf
```

Replace AllowOverride None values with <b>AllowOverride All</b>.

```php
ServerName localhost

# Sets the default security model of the Apache2 HTTPD server. It does
# not allow access to the root filesystem outside of /usr/share and /var/www.
# The former is used by web applications packaged in Debian,
# the latter may be used for local directories served by the web server. If
# your system is serving content from a sub-directory in /srv you must allow
# access here, or in any related virtual host.
<Directory />
        Options FollowSymLinks
        AllowOverride All
        Require all denied
</Directory>

<Directory /usr/share>
        AllowOverride All
        Require all granted
</Directory>

<Directory /var/www/>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
</Directory>
```

Restart Apache2

```php
sudo service apache2 restart
```


### Installation Sublime-Text-3 for Ubuntu

```php
sudo add-apt-repository ppa:webupd8team/sublime-text-3
sudo apt-get update
sudo apt-get install sublime-text-installer
```

**Note** : To install plugins for sublime text you need install package control library.

### Installation Sublime Package Control

Package Control:

<kbd>Preferences > Browse Packages</kbd>

* Browse up a folder and then into the Installed <b>Packages/</b> folder
* Download <a href="https://sublime.wbond.net/Package%20Control.sublime-package" target="_blank">Package Control.sublime-package</a> and copy it into the Installed Packages/ directory
* Restart Sublime Text


### Read Warmup/Package/README.md files

Some popular sublime packages

* Codesniffer
* PhpMd

<a href="https://sublime.wbond.net/" target="_blank">Go sublime packages directory</a>


### Installation Git

<a href="https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu-14-04">https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu-14-04</a>

#### Git Ssh Key Setup

<a href="https://help.github.com/articles/generating-ssh-keys">https://help.github.com/articles/generating-ssh-keys</a>


### Php Extensions

Tested on Ubuntu 14.04 

You should add "extension=name.so" to your php.ini extension

```php
cd /etc/php5/apache2/mods-available
```

Create your ini file using your text editor

```php
vim name.ini
```

Paste below the lines

```php
; configuration for php NAME module
; priority=20
extension=name.so
```

Enable your extension

```php
php5enmod name
```

Restart apache

```php
sudo service apache2 restart
```
