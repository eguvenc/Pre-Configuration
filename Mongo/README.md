
## Installing Mongo Server

https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-14-04
https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-16-04

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

## Installing RockMongo (Php mongo admin)

Download <a href="http://obullo.com/utils/rockmongo.zip">Rockmongo.zip</a> and extract it to your /var/www/html/ folder.

Then edit config.php.

Browse

```
http://localhost/rockmongo
```

username: admin <br />
password: admin

## Setting Root Password

Enter to mongo shell

```
sudo mongo
```

Select admin db

```
use admin
```

Next, create your root user by issuing this command in the shell. We will name the user admin and grant the user the root role:

```
db.createUser({user:"root", pwd:"secret_password", roles:[{role:"root", db:"admin"}]})
```

Now your admin user having the root role is created. MongoDB doesn’t have the exact same concept of the root user present in SQL databases. Instead, you can create as many users and assign them the root role, which will give them all privileges. You can exit the database shell:

```
exit
```

Now open the file /etc/mongodb.conf using your favorite editor and if you have this line uncomment it:

```
#auth = true
```

Finally, you can now log into the admin database like so:

```
mongo -u admin -p secret_password --authenticationDatabase admin
```
