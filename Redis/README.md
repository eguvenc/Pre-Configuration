
## Redis

-----

## Installing Redis-Server under the Ubuntu 14.04

```php
sudo apt-get install redis-server
```

## Redis Configuration

All Redis configuration options can be specified in the redis.conf file located at /etc/redis/redis.conf. You may wish to make a copy of this file before editing it, to retain default values in case of a problem down the line:

```php
cp /etc/redis/redis.conf /etc/redis/redis.conf.default
```

Detailed configuration at here <a href="https://www.linode.com/docs/databases/redis/redis-on-ubuntu-12-04-precise-pangolin">https://www.linode.com/docs/databases/redis/redis-on-ubuntu-12-04-precise-pangolin</a>

To edit your conf file

```php
vim /etc/redis/redis.conf
```

## Adding Password

Open redis.conf then uncomment below the line and set your password.

```php
# requirepass foobared
```

Restart your server

```php
service redis-server restart
```

Example config file

```php
daemonize yes
pidfile /var/run/redis.pid
logfile /var/log/redis.log

port 6379
bind 127.0.0.1
timeout 300

loglevel notice
```

## Default configuration options

databases 16

save 900 1
save 300 10
save 60 10000

rdbcompression yes
dbfilename dump.rdb

appendonly no

## Installing Php Redis-Client

```php
sudo apt-get install php5-redis
```

## Installing PhpRedisAdmin

```php
cd /var/www
git clone https://github.com/ErikDubbelboer/phpRedisAdmin.git
cd phpRedisAdmin
git clone https://github.com/nrk/predis.git vendor
```

Save <b>includes/config.sample.inc.php</b> as <b>config.inc.php</b>

```php
<?php
// Copy this file to config.inc.php and make changes to that file to customize your configuration.

$config = array(
  'servers' => array(
    array(
      'name'   => 'local server', // Optional name.
      'host'   => '127.0.0.1',
      'port'   => 6379,
      'filter' => '*',

      // Optional Redis authentication.
      //'auth' => 'redispasswordhere' // Warning: The password is sent in plain-text to the Redis server.
    ),

    /*array(
      'host' => 'localhost',
      'port' => 6380
    ),*/

    /*array(
      'name'      => 'local db 2',
      'host'      => 'localhost',
      'port'      => 6379,
      'db'        => 1,             // Optional database number, see http://redis.io/commands/select
      'filter'    => 'something:*', // Show only parts of database for speed or security reasons.
      'seperator' => '/',           // Use a different seperator on this database.
      'flush'     => false,         // Set to true to enable the flushdb button for this instance.
      'charset'   => 'cp1251',      // Keys and values are stored in redis using this encoding (default utf-8).
    ),*/
  ),


  'seperator' => ':',


  // Uncomment to show less information and make phpRedisAdmin fire less commands to the Redis server. Recommended for a really busy Redis server.
  //'faster' => true,


  // Uncomment to enable HTTP authentication
  /*'login' => array(
    // Username => Password
    // Multiple combinations can be used
    'admin' => array(
      'password' => 'adminpassword',
    ),
    'guest' => array(
      'password' => '',
      'servers'  => array(1) // Optional list of servers this user can access.
    )
  ),*/


  // You can ignore settings below this point.

  'maxkeylen'           => 100,
  'count_elements_page' => 100
);

?>
```

Visit

```php
http://localhost/phpRedisAdmin/
```
