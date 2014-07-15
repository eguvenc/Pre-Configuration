
## Enabling Multiline Doc Blocks

-----

<kbd>Preferences > Key Bindings-User</kbd>

Enables multi toggle comments with <b>[ctrl+shift+c]</b> shortcuts.

```php
[
	{ "keys": ["ctrl+shift+c"], "command": "toggle_comment", "args": { "block": false } },
	{ "keys": ["ctrl+shift+a"], "command": "toggle_comment", "args": { "block": true } },
	{ "keys": ["alt+m"], "command": "markdown_preview", "args": {"target": "browser", "parser":"markdown"} },
]
```

## Enabling Tab Alignment

<kbd>Preferences > Package-Control > Install Package > Alignment</kbd>

Enables auto tab alignment with <b>[ctrl+alt+a]</b> shortcuts.