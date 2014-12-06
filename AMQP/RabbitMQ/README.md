
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

### Download the latest rabbitmq-c library

```php
wget https://github.com/alanxz/rabbitmq-c/releases/download/v0.5.2/rabbitmq-c-0.5.2.tar.gz
tar -zxvf rabbitmq-c-0.5.2.tar.gz
cd rabbitmq-c-0.5.2/
./configure
make
sudo make install
```

### Install essential libraries

```php
sudo apt-get install build-essential libncursesw5-dev libc6-dev libtool
```

### Configure, compile and install

```php
autoreconf -i && ./configure && make && sudo make install
```

```php
sudo apt-get install librabbitmq-dev php-pear php5-dev
```

```php
pecl install amqp
```

You should add "extension=amqp.so" to your php.ini extension

```php
cd /etc/php5/mods-available
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

To Add a new root user and permissions

```php
rabbitmqctl add_user root 123456
rabbitmqctl set_permissions root ".*" ".*" ".*"
```