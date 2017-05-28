---
title: Socialite
taxonomy:
    category:
        - docs
---

Alles über Laravel Socialite

# Installation

Das [offizielle Socialite Package](https://github.com/laravel/socialite) enthält Provider für:
- Facebook, 
- Twitter, 
- Google
- LinkedIn
- GitHub
- Bitbucket

Es gibt eine [inoffizielle Sammlung von Providern](https://socialiteproviders.github.io/)




### Require it
```
composer require laravel/socialite
```

#### Add Provider
```
'providers' => [
    // Other service providers...

    Laravel\Socialite\SocialiteServiceProvider::class,
],
```

**Oder den Socialite Providers**  
dafür muss aber der "original" Provider auskommentiert/ entfernt werden
```
'providers' => [
    // Other service providers...
    // Laravel\Socialite\SocialiteServiceProvider::class,
    \SocialiteProviders\Manager\ServiceProvider::class,
],
```



#### Add Facade
```
'Socialite' => Laravel\Socialite\Facades\Socialite::class,
```

#### Add Provider
at: _config/provider.php_

```
'github' => [
    'client_id' => env('GITHUB_CLIENT_ID'),
    'client_secret' => env('GITHUB_CLIENT_SECRET'),
    'redirect' => env('GITHUB_REDIRECT'),
],
```

at: _.env_
```
GITHUB_CLIENT_ID=
GITHUB_CLIENT_SECRET=
GITHUB_REDIRECT
```

#### Inoffizielle Provider

```
composer require socialiteproviders/PROVIDERNAME
```

Die Einbindung erfolgt über Events.
at: _app/Providers/EventServiceProvider.php_

```
protected $listen = [
    \SocialiteProviders\Manager\SocialiteWasCalled::class => [
        // add your listeners (aka providers) here
        'SocialiteProviders\Twitch\TwitchExtendSocialite@handle',
    ],
];
```

Für jeden Provider muss ein extra Handler hinzugefügt werden.
