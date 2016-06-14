
https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-14-04

Download <a href="http://obullo.com/utils/rockmongo.zip">Rockmongo.zip</a> and extract your www root.

Then edit config.php.

## Installing PHP Mongo Extension

```
sudo pecl install mongo
```

```
sudo touch /etc/php5/mods-available/mongo.ini
```

```
extension=mongo.so
```

Then enable mongo module.

```
php5enmod mongo
```

Restart your server

```
service apache2 restart
```