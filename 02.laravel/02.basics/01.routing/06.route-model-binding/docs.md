---
title: Route Model Binding
taxonomy:
    category:
        - docs
---

## Implicit Binding

```
Route::get('api/users/{user}', function (App\User $user) {
    return $user->email;
});
```

## Schlüssel

```
public function getRouteKeyName()
{
    return 'slug';
}
```

## Explicit Binding

@ _RouteServiceProvider

```php
public function boot()
{
    parent::boot();

    Route::model('user', App\User::class);
}
```

Von nun an sind alle Routen die den Parameter `user` behinhalten automatisch an das User Model gebunden
```
Route::get('profile/{user}', function (App\User $user) {
    //
});
```

```
public function boot()
{
    parent::boot();

    Route::bind('user', function ($value) {
        return App\User::where('name', $value)->first();
    });
}
```