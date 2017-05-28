---
title: Laravel Installieren
published: true
date: '28-05-2017 11:24'
publish_date: '27-05-2017 16:39'
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
menu: Installation
slug: installation
---

## Mit Composer

```bash
composer create-project laravel/laravel name
```

## Mit dem Laravel Installer

Zuerst den Laravel Installer global installieren.

```bash
composer global require "laravel/installer"
```

danach den Pfad zur ausführbaren Datei im System bekannt machen (Path).
Ab dann kann man den einfacheren Befehl benutzen.

```bash
laravel new blog
```

## Eine Development Version installieren

```bash
composer create-project laravel/laravel myproject "dev-develop"
```