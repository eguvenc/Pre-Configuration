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

Installation steps:

- Download the desired PHP x86 version: http://windows.php.net/download/
- Unzip the files into C:/PHP/
- Open Sublime.
- Press CTRL+SHIFT+P
- Enter  Install Package and choose Package Control: Install Package
- Enter SublimeLinter and click on enter to install.
- Do the same in step 5 and 6 for the package SublimerLinter-PHP.
- Open Preferences -> Package Settings -> SublimeLinter -> Settings – User
- Change in the paths key “windows”: [] to “windows”: [“C:/PHP/”]
- Save the file and restart Sublime.

https://www.yourwebhoster.eu/2015/10/26/install-sublimelinter-php-on-windows/
https://pupungbp.com/activating-php-sublimetext-3-error-highlighting-under-windows-10/
