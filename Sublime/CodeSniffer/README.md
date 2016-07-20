
## PHP Code Sniffer

-----

PHP_CodeSniffer is a PHP5 script that tokenises and "sniffs" PHP, JavaScript and CSS files to detect violations of a defined coding standard. It is an essential development tool that ensures your code remains clean and consistent. It can also help prevent some common semantic errors made by developers.

#### Installation for Ubuntu


```php
$ pear channel-discover pear.phpmd.org
$ pear channel-discover pear.pdepend.org
$ pear install --alldeps phpmd/PHP_PMD
$ pear install PHP_CodeSniffer

```

Install Code Sniffer

<kbd>Preferences > Package-Control > Install Package > PHPcs</kbd>

Then

#### Enable it for sublime

Go <kbd>Preferences > Package Settings > PHP Code Sniffer > Settings - User</kbd>

```php
{
    "phpcs_executable_path": "/usr/bin/phpcs",
    "phpcs_show_quick_panel": false,
 
    "phpcs_additional_args": {
        "--standard": "PSR2",
        "-n": ""
    },
    // Execute phpmd
    "phpmd_run": true,

     // Execute the phpmd on file save
    "phpmd_command_on_save": true,

     // It seems python/sublime cannot always find the phpmd application
     // If empty, then use PATH version of phpmd, else use the set value
    "phpmd_executable_path": "/usr/bin/phpmd",

     // Additional arguments you can specify into the application
     //
     // Example:
     // {
     //         "codesize,unusedcode"
     // }
    "phpmd_additional_args": {
        "codesize,unusedcode": ""
    },
}
```

Paste it above the text.

### To fix code errors with Phpcbf

Configure a Build Command in Sublime Text 3

* Open Sublime Text
* Got to Tools > Build System > New Build System…

Enter the following command and save:

```php
{
    "shell_cmd": "phpcbf --standart=PSR2 $file"
}
```

That’s it. When you run this command, phpcbf will apply psr-2 standards to the current file you have open.

Run the command by pressing <kbd>Control + B</kbd>

### Another Alternative Php-Cs-Fixer

<a href="http://www.codehops.com/2016/04/07/setup-php-cs-fixer-for-sublime-text-3-on-os-x.html">http://www.codehops.com/2016/04/07/setup-php-cs-fixer-for-sublime-text-3-on-os-x.html</a>

