---
title: Events
taxonomy:
    category:
        - docs
---

Laravel Digging Deeper: Events

### 1. Events registrieren

in: _App/Providers/EventServicePorvider.php_ die Events und die Handler registireren

```php
protected $listen = [
	'App\Events\SomeEvent' => [ 
    	'App\Listeners\EventListener',
    ],
];
```

### 2. Die Events und die Handler erstellen lassen

Dieser Befehl schaut in den EventServiceProvider und erstellt alle dort angegebenen Events und Listener

```bash
php artisan event:generate
```

### 3. Die Events und die Handler füllen



#### Laravel's eingebaute Events

**Login**

```php
'Illuminate\Auth\Events\Login' => [
	'App\Listeners\HandleSuccessfulLogin',
],
```