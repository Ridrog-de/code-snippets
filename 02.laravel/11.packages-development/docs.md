---
title: Laravel Packete erstellen
published: true
date: '28-05-2017 11:24'
publish_date: '28-05-2017 11:24'
taxonomy:
    category:
        - docs
    tag:
        - laravel
    language:
        - php
    version:
        - '5.4'
    framework:
        - laravel
menu: Package Development
slug: package-development
---

#### Ordnerstruktur

packages/*Vendor*/*packetname*/scr

#### Init composer

_in: packages/*Vendor*/*Packetname*/_

```
composer init
```

#### Autoloading

```
"*Vendor*\\*Packetname*\\": "packages/*Vendor*/*Packetname*/src"
```

anschließend

```
composer dump-autoload
```

#### ServiceProvider

```
php artisan make:provider PacketnameServiceProvider
```

diese Datei dann in die Packages kopieren und den Namespace ändern

#### ServiceProvider einbinden

_in: config/app_

