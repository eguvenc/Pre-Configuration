
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

Obullo use <b>PEAR</b> coding standarts.

```php
{
    "phpcs_executable_path": "/usr/bin/phpcs",
    "phpcs_show_quick_panel": false,
 
    "phpcs_additional_args": {
        "--standard": "PEAR",
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