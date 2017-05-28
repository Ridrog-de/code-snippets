---
title: 'Setup Passport'
taxonomy:
    category:
        - docs
---

#### Puplish the Views

```
php artisan vendor:publish --tag=passport-components
```

#### Register the Vue Components

```
Vue.component(
    'passport-clients',
    require('./components/passport/Clients.vue')
);

Vue.component(
    'passport-authorized-clients',
    require('./components/passport/AuthorizedClients.vue')
);

Vue.component(
    'passport-personal-access-tokens',
    require('./components/passport/PersonalAccessTokens.vue')
);
```

#### Include the View Templates

```
<passport-clients></passport-clients>
<passport-authorized-clients></passport-authorized-clients>
<passport-personal-access-tokens></passport-personal-access-tokens>
```

#### Die Eigene API benutzen

Einfach der webmiddleware CreateFreshApiToken hinzufügen
in: _app/Http/Kernel.php_

```
\Laravel\Passport\Http\Middleware\CreateFreshApiToken::class,
```

##### Dann noch ein Token erstellen

```
php artisan passport:client --personal
```
