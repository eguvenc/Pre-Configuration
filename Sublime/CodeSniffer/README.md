
## PHP Code Sniffer

-----

<kbd>Preferences > Package Settings > PHP Code Sniffer > Settings - User</kbd>

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