
https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-14-04

Download <a href="http://obullo.com/utils/rockmongo.zip">Rockmongo.zip</a> and extract your www root.

Then edit config.php.

## Installing PHP Mongo Extension

```
sudo pecl install mongo
```

```
sudo touch /etc/php5/conf.d/mongo.ini
```

```
extension=mongo.so
```
