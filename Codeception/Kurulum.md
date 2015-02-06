Kurulum
===================

Codeception kurulumu iki farklı şekilde yapılmaktadır.

- codecept.phar
- composer.phar
 
Kullanım açısından bir birlerine karşı üstünlükleri yoktur. Tamamen tercih sebebidir.

codecept.phar
-------------

Komut satırından projenin ana (root) dizinine gidelim ve aşağıdaki komutu çalıştıralım.
codecept.phar

```sh
  $ wget http://codeception.com/codecept.phar
  $ php codecept.phar
```

Global:
```sh
$ mv /usr/local/bin/codecept codecept.phar
$ codecept
```
composer.phar
-------------
Composer ile kurulum yapmak istersek öncesinde composer paketini projemize dahil etmemiz gerekiyor. Projenizde composer kurulu ise bu adımı geçebilirsiniz.

```sh
$ curl -sS https://getcomposer.org/installer | php
$ php composer.phar require "codeception/codeception:*"
$ vendor/bin/codecept
```

İstersek yukarıdaki komutla bir kısaltma verebiliriz.
```sh
$ alias codecept="vendor/bin/codecept"
```

Global:
```sh
$ mv /usr/local/bin/composer composer.phar
$ composer
```

> **Note:**
Global kullanım için indirdiğiniz  (composer.phar yada codecept.phar) dosyayı **/usr/local/bin/** klasörüne taşımanız gerekmektedir.

Sıradaki yapmamız gereken işlem **bootstrap**  komutunu çalıştırarak codeception çalışma ortamını hazır hale getirmek. Şayet testlerimizi farklı dizinlerde çalıştırmak istiyorsak bu kısım önemli bizim için.

Varsayılan:
```sh
$ codecept bootstrap
```

Testlerimiz farklı bir dizinden çalıştırılacak ise:
```sh
$  codecept bootstrap /path/to/my/project
```

Yukardaki adımları uyguladıysanız kurulum tamamlandı demektir.
Projenizin ana (root) dizinindeki **tests** klasörünü inceleyiniz.

Enjoy testing!
---