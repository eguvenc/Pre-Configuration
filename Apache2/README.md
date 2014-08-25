

## Creating Apache2 Vhost File under the Ubuntu

-----

To create new virtual host first we need to add it <b>/etc/hosts</b> file. Following the example we have a project called <b>test.example.com</b> and we create vhost for it.

Open your hosts file.


```php
vim /etc/hosts
```

Add your virtual host

```php
127.0.0.1       localhost
127.0.1.1       my-desktop
127.0.1.1       framework
127.0.1.1       test.example.com
```

Then save and exit

Now we need create vhost file to under the <b>/etc/apache2</b> folder.

Go this directory

```php
cd /etc/apache2
```

List all files with <b>ll</b> command

```php
ll

drwxr-xr-x   8 root root  4096 Ağu 19 15:08 ./
drwxr-xr-x 139 root root 12288 Ağu 25 14:33 ../
-rw-r--r--   1 root root  7170 Ağu 19 15:08 apache2.conf
drwxr-xr-x   2 root root  4096 Ağu 19 13:27 conf-available/
drwxr-xr-x   2 root root  4096 Ağu 19 13:27 conf-enabled/
-rw-r--r--   1 root root  1782 Oca  3  2014 envvars
-rw-r--r--   1 root root 31063 Oca  3  2014 magic
drwxr-xr-x   2 root root 12288 Ağu 19 13:27 mods-available/
drwxr-xr-x   2 root root  4096 Ağu 19 15:05 mods-enabled/
-rw-r--r--   1 root root   320 Oca  7  2014 ports.conf
drwxr-xr-x   2 root root  4096 Ağu 25 11:10 sites-available/
drwxr-xr-x   2 root root  4096 Ağu 25 11:10 sites-enabled/
```

Enter to available web sites


```php
cd sites-available
```

List all

```php
ll

drwxr-xr-x 2 root root 4096 Ağu 25 11:10 ./
drwxr-xr-x 8 root root 4096 Ağu 19 15:08 ../
-rw-r--r-- 1 root root 1332 Oca  7  2014 000-default.conf
-rw-r--r-- 1 root root 6437 Oca  7  2014 default-ssl.conf
-rw-r--r-- 1 root root 1337 Ağu 19 14:39 framework.conf
```

Copy <b>000-default.conf</b> as <b>test.example.com.conf</b>

```php
cp 000-default.conf test.example.com.conf
```

Then edit your <b>test.example.com.conf</b> file

```php
vim test.example.com.conf
```

```php
<VirtualHost *:80>
        # The ServerName directive sets the request scheme, hostname and port that
        # the server uses to identify itself. This is used when creating
        # redirection URLs. In the context of virtual hosts, the ServerName
        # specifies what hostname must appear in the request's Host: header to
        # match this virtual host. For the default virtual host (this file) this
        # value is not decisive as it is used as a last resort host regardless.
        # However, you must set it for any further virtual host explicitly.
        #ServerName www.example.com

        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/html

        # Available loglevels: trace8, ..., trace1, debug, info, notice, warn,
        # error, crit, alert, emerg.
        # It is also possible to configure the loglevel for particular
        # modules, e.g.
        #LogLevel info ssl:warn

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        # For most configuration files from conf-available/, which are
        # enabled or disabled at a global level, it is possible to
        # include a line for only one particular virtual host. For example the
        # following line enables the CGI configuration for this host only
        # after it has been globally disabled with "a2disconf".
        #Include conf-available/serve-cgi-bin.conf
</VirtualHost>

# vim: syntax=apache ts=4 sw=4 sts=4 sr noet
```

Set your <b>serverName</b> and <b>DocumentRoot</b>


```php
<VirtualHost *:80>
        # The ServerName directive sets the request scheme, hostname and port that
        # the server uses to identify itself. This is used when creating
        # redirection URLs. In the context of virtual hosts, the ServerName
        # specifies what hostname must appear in the request's Host: header to
        # match this virtual host. For the default virtual host (this file) this
        # value is not decisive as it is used as a last resort host regardless.
        # However, you must set it for any further virtual host explicitly.

        ServerName test.example.com

        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/test

        # Available loglevels: trace8, ..., trace1, debug, info, notice, warn,
        # error, crit, alert, emerg.
        # It is also possible to configure the loglevel for particular
        # modules, e.g.
        #LogLevel info ssl:warn

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        # For most configuration files from conf-available/, which are
        # enabled or disabled at a global level, it is possible to
        # include a line for only one particular virtual host. For example the
        # following line enables the CGI configuration for this host only
        # after it has been globally disabled with "a2disconf".
        #Include conf-available/serve-cgi-bin.conf
</VirtualHost>

# vim: syntax=apache ts=4 sw=4 sts=4 sr noet
```

Then save the file and restart your apache2


```php
service apache2 restart
```

Thats It !

If you use <b>.htaccess</b> file you also need do below the things for once.


### Enable Apache2 Mode Rewrite (.htaccess) and Setting Your ServerName

```php
sudo a2enmod rewrite
```

Go

```php
vim /etc/apache2/apache2.conf
```

Replace AllowOverride None values with <b>AllowOverride All</b>.

Also we set serverName to prevent service restart errors.

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

Thats It !