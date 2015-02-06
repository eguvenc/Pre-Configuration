
Acceptance Tests
======
İlk olarak tests ayarlarımızı yapılandıralım.

![enter image description here](https://lh4.googleusercontent.com/-alf64_6IB5Q/VNTR9SluSYI/AAAAAAAAAL8/powc2uebO5A/s0/68747470733a2f2f6c68362e676f6f676c6575736572636f6e74656e742e636f6d2f2d71492d723853416169636f2f564c354249347163717a492f4141414141414141414b452f2d61436c334b39644f57732f73302f53637265656e73686f742b66726f6d2b323031352d30312d32302b31303a34343a30362e706e67.png "68747470733a2f2f6c68362e676f6f676c6575736572636f6e74656e742e636f6d2f2d71492d723853416169636f2f564c354249347163717a492f4141414141414141414b452f2d61436c334b39644f57732f73302f53637265656e73686f742b66726f6d2b323031352d30312d32302b31303a34343a30362e706e67.png")

Projemizin ana (root) dizinindeki tests klasörü içinde acceptance.suit.yml dosyamızı yukarıdaki şekilde yapılandırdık.

Ardından yeni bir test sınıfı oluşturalım:
```sh
$ codecept generate:cept acceptance First
```
Komutu çalıştırdıktan sonra **tests/acceptance** klasörü içinde **FirstCept.php** adında yeni bir dosyanın oluştuğunu göreceksiniz.

```php
<?php
	$I = new AcceptanceTester($scenario);
	$I->wantTo('sign in');
	$I->amOnPage('/login');
	$I->fillField('username', 'davert');
	$I->fillField('password', 'qwerty');
	$I->click('LOGIN');
	$I->see('Welcome, Davert!');
?>
```

