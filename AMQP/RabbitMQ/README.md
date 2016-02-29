
## RabbitMQ

-----

## Installing RabbitMQ-Server under the Ubuntu 14.04

```php
sudo apt-get remove rabbitmq-server
```

```php
sudo apt-get install python-software-properties
sudo add-apt-repository "deb http://www.rabbitmq.com/debian/ testing main"
```

```php
wget http://www.rabbitmq.com/rabbitmq-signing-key-public.asc
sudo apt-key add rabbitmq-signing-key-public.asc
sudo apt-get update
sudo apt-get install rabbitmq-server
sudo service rabbitmq-server start
sudo rabbitmq-plugins enable rabbitmq_management
```

```php
sudo service rabbitmq-server restart
```

### Install essential libraries

```php
sudo apt-get install build-essential libncursesw5-dev libc6-dev libtool
```

```php
sudo apt-get install librabbitmq-dev php-pear php5-dev
```

### Clean old versions

```php
locate librabbitmq.so

/usr/local/lib/librabbitmq.so
/usr/local/lib/librabbitmq.so.1
/usr/local/lib/librabbitmq.so.1.2.1

rm -rf /usr/local/lib/librabbitmq.so*

updatedb
locate librabbitmq.so
```

### Configure, compile and install

```php
apt-get install php-pear
pecl uninstall amqp

apt-get install aptitude
aptitude install libtool
aptitude install pkg-config
cd /tmp
rm -rf rabbitmq-c
git clone -b v0.5.2 git://github.com/alanxz/rabbitmq-c.git
cd rabbitmq-c
autoreconf -i && ./configure && make && make install
pecl install amqp-1.4.0
```

```php
cd /etc/php5/mods-available
ll
```

Create ini file using your text editor

```php
vim amqp.ini
```

Paste below the lines

```php
; configuration for php AMQP module
; priority=20
extension=amqp.so
```

Enable amqp extension

```php
php5enmod amqp
```

```php
sudo service apache2 restart
```

### Admininstration

<a href="http://localhost:15672/">http://localhost:15672/</a> 

Default panel user is <b>"guest"</b> and password is <b>"guest"</b>

To add a new user and permissions

```php
rabbitmqctl add_user root 123456
rabbitmqctl set_permissions root ".*" ".*" ".*"
rabbitmqctl set_user_tags root administrator
```
