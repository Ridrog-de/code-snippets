---
title: 'Install Passport'
taxonomy:
    category:
        - docs
---

#### 1. Require it

```
composer require laravel/passport
```

#### 2. Service Provider

in: _config/app.php_

```
Laravel\Passport\PassportServiceProvider::class,
```

#### 3. Migrate

```
php artisan migrate
```

#### 4. Install

```
php artisan passport:install
```

#### 5. Add the trait to the user Model

```
use Laravel\Passport\HasApiTokens;
```

and

```
use HasApiTokens, Notifiable;
```

#### 6. Add the Routes

in _app/Providers/AuthServiceProvider_

```
use Laravel\Passport\Passport;
```


in der ```boot``` method

```
Passport::routes();
```

#### 7. Change the API Guards to Passport

in _config/auth.php_

```
'guards' => [
        'web' => [
            'driver' => 'session',
            'provider' => 'users',
        ],

        'api' => [
            'driver' => 'passport',
            'provider' => 'users',
        ],
    ],
```