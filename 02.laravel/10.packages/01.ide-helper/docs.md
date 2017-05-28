---
title: 'IDE Helper Package'
published: true
date: '28-05-2017 11:14'
publish_date: '28-05-2017 11:14'
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
menu: IDE Helper
slug: ide-helper
---

### 1. Installieren

```bash
composer require barryvdh/laravel-ide-helper
```

### 2. Service Provider
in: _config/app.php_

```php 
Barryvdh\LaravelIdeHelper\IdeHelperServiceProvider::class,
```

### 3. Helper File erstellen

```bash
php artisan ide-helper:generate
```