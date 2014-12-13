
## Enabling Doc Blocker

-----

DocBlocker comes to the rescue with some automated documentation macros you might be familiar with if you have experience with a larger IDE like Eclipse. Now there is no excuse !

<kbd>Preferences > Package-Control > Install Package > DocBlockr</kbd>

Enables auto doc blocks and comments like below the example.

```php

    /*
    Press Enter Afrer Doc Block
     */
    public function __construct($c, $queue, $config = array())
    {

    }


```

The below shows the default output after a simple /** invocation, now all we need to do is fill in the blanks.

```php
    /**
     * [__construct description]
     * @param [type]
     * @param [type]
     * @param array
     */
    public function __construct($c, $queue, $config = array())
    {
        // auto doc blocks for parameters and comments ...
    }
```
