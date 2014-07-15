
## PHP MD

-----

This is the project site of PHPMD. It is a spin-off project of <a href="http://pdepend.org/">PHP Depend</a> and aims to be a PHP equivalent of the well known Java tool <a href="http://pmd.sourceforge.net/">PMD</a>. PHPMD can be seen as an user friendly and easy to configure frontend for the raw metrics measured by PHP Depend.

<a href="http://phpmd.org/rules/index.html">Rules</a>
<a href="http://www.brandonsavage.net/code-complexity-and-clean-code/">Code complexity and clean code</a>
<a href="https://www.codacy.com/public/sonata-project/SonataAdminBundle.git/master/file/%2FController%2FCRUDController.php/issues">Example Errors</a>

### Installing as a PEAR package

The preferred way to install PHPMD should be the PEAR installer and PHPMD's PEAR channel, where you will always find the latest stable version. Because PHPMD heavily relies on metrics measured with PHP Depend you must also discover this project's PEAR Channel. Just enter:

```php
pear channel-discover pear.phpmd.org
pear channel-discover pear.pdepend.org
pear install --alldeps phpmd/PHP_PMD
```

### From the github repository

```php
If you like to participate on the social coding plattform <a href="http://pear.php.net/manual/en/installation.php">GitHub</a>, you can use PHPMD's mirror to fork and contribute to PHPMD.
```

<kbd>git clone git://github.com/phpmd/phpmd.git</kbd>

Then cd into the checkout directory initialize the referenced sub modules:

<kbd>cd phpmd ~/phpmd $ git submodule update --init</kbd>

This installs the build framework used by PHPMD. To initialize PHPMD's requirements you should now invoke Ant with the initialize target:

<kbd>~/phpmd $ ant initialize</kbd>

This command installs the dependencies used by PHPMD. Please not that this command will produce a lot of output on the shell.

### Installing via Composer

Create a composer.json file in your project directory and add PHPMD as a required dependency:

```php
{
	"require": {
		"phpmd/phpmd" : "1.4.*"
	}
}
```