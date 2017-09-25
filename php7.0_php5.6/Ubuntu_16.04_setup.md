
## INSTALLATION Php7.0 & Php5.6 under the Same Machine

```
sudo add-apt-repository ppa:ondrej/php
```

```
sudo apt-get update
```

```
sudo apt-get install php5.6 php7.0
```

Switching versions

```
sudo a2dismod php5.6
sudo a2enmod php7.0
sudo service apache2 restart
```

Working with extensions

```
sudo phpenmod extension
php -m
```

Working with cli

```
sudo update-alternatives --config php
```

Choose your version.

```
  Selection    Path             Priority   Status
------------------------------------------------------------
  0            /usr/bin/php7.0   70        auto mode
* 1            /usr/bin/php5.6   56        manual mode
  2            /usr/bin/php7.0   70        manual mode

Press <enter> to keep the current choice[*], or type selection number: 1
```

for more details

<a href="http://www.lornajane.net/posts/2016/php-7-0-and-5-6-on-ubuntu"></a>


