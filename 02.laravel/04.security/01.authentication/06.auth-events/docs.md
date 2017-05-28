---
title: 'Auth Events'
taxonomy:
    category:
        - docs
---

#### Events von Register, Login usw nutzen
Laravel hat einige Events bereits eingebaut. Mehr siehe Übersicht

1. Event und Listener definieren
2. mit Artisan ```php artisan event:generate``` die Dateien erstellen lassen
3. Die Listener füllen


#### Übersicht

```
protected $listen = [
    'Illuminate\Auth\Events\Registered' => [
        'App\Listeners\LogRegisteredUser',
    ],

    'Illuminate\Auth\Events\Attempting' => [
        'App\Listeners\LogAuthenticationAttempt',
    ],

    'Illuminate\Auth\Events\Authenticated' => [
        'App\Listeners\LogAuthenticated',
    ],

    'Illuminate\Auth\Events\Login' => [
        'App\Listeners\LogSuccessfulLogin',
    ],

    'Illuminate\Auth\Events\Failed' => [
        'App\Listeners\LogFailedLogin',
    ],

    'Illuminate\Auth\Events\Logout' => [
        'App\Listeners\LogSuccessfulLogout',
    ],

    'Illuminate\Auth\Events\Lockout' => [
        'App\Listeners\LogLockout',
    ],
];
```