---
title: 'Regular Expression Routing'
published: true
date: '28-05-2017 11:24'
publish_date: '27-05-2017 16:39'
taxonomy:
    category:
        - 'docs'
    tag:
        - 'laravel'
    language:
        - 'php'
    version:
        - '5.4'
    framework:
        - 'laravel'
menu: 'Regular Expression'
slug: 'regular-expression'
---

```
Route::get('user/{name}', function ($name) {
    //
})->where('name', '[A-Za-z]+');
```

```
Route::get('user/{id}', function ($id) {
    //
})->where('id', '[0-9]+');
```

```
Route::get('user/{id}/{name}', function ($id, $name) {
    //
})->where(['id' => '[0-9]+', 'name' => '[a-z]+']);
```

## Globale Regeln

@ _RouteServiceProvider_

```
public function boot()
{
    Route::pattern('id', '[0-9]+');

    parent::boot();
}
```

Folgende Route wird nur noch ausgeführt wenn die ID ein Zahlenwert ist

```
Route::get('user/{id}', function ($id) {
    // Only executed if {id} is numeric...
});
```