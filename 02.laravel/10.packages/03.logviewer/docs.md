---
title: LogViewer
taxonomy:
    category:
        - docs
---

### ARCANEDEV/LogViewer

[Github](https://github.com/ARCANEDEV/LogViewer)

#### Requirements

Set the log to "daily" at "config/app.php"

#### Install

1. Install with Composer
```
composer require arcanedev/log-viewer
```

2. Add the Provider in "config/app.php"
```
Arcanedev\LogViewer\LogViewerServiceProvider::class,
```

3. Puplish the views and the config
```
php artisan log-viewer:publish
```

Man kann nun die Logs und /log-viewer anschauen

#### Config

in "config/log-viewer.php" alles nötige anpassen
- Route prefix
- middleware
    ```'middleware' => ['web', 'auth', 'admin'],```
    
#### Layout anpassen

Das einfachste ist es, einfach alles so zu lassen und einfach einen Link zurück zum Adminbereich einzufügen