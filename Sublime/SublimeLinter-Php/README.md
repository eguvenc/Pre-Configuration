If you haven’t installed SublimeLinter, you can do that via Package Control, SublimeLinter, and SublimeLinter-PHP.

After successfully installed, go to Preferences > Package Settings > SublimeLinter > Settings – User 

Add PHP Executable folder to the Path, in my case php.exe located in C:\wamp\bin\php\php5.5.12\

```
"paths": {
            "linux": [],
            "osx": [],
            "windows": [
                "C:/wamp/bin/php/php5.5.12/"
            ]
        },
```

Save the file.

The last steps are making a difference with the previous version of Windows.

*Going to your PC’s Control Panel.
*Select System.
*Select Advanced system settings.
*From System Properties, select Environment Variables.
*Under System Variables find the variable Path. Select it and click edit.
*At the end of the Variable Value add your PHP’s path location. In my case it was C:\wamp\bin\php\php5.5.12\. All paths are separated by a ; so be sure to add one, if there isn’t already, followed by your PHP’s file path.
*Restart your Sublime Text editor.

https://pupungbp.com/activating-php-sublimetext-3-error-highlighting-under-windows-10/
