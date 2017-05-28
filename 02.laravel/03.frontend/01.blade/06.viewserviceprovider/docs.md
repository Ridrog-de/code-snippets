---
title: 'Daten in allen Views teilen'
---

#### Einen ServiceProvider erstellen

```
php artisan make:provider ViewServiceProvider
```

#### Die Funktion die die Daten holt schreiben
und in die boot Methode des ViewServiceProvider schreiben

```
view()->composer('layouts.app.navbar', function($view){
    $view->with('test', 'Hallo');
});
```

#### Den Serviceprovider einbinden

in: _config/AppServiceProvider_

```
App\Providers\ViewServiceProvider::class,
```