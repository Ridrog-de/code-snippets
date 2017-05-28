---
title: 'Named Routing'
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
menu: 'Named'
slug: 'named'
---


Benannte Routen kann man mit ```->name('nameDerRoute')``` erstellen.

```
Route::get('user/profile', function () {
    //
})->name('profile');
```

```
Route::get('user/profile', 'UserController@showProfile')->name('profile');
```

## URLs generieren

```
$url = route('profile');
```

**Weiterleitung**

```
return redirect()->route('profile');
```

**Parameter**

```
Route::get('user/{id}/profile', function ($id) {
    //
})->name('profile');
```

```
$url = route('profile', ['id' => 1]);
```


## Die aktive Seite setzen

```
<li class="{{ Route::is('yournamedroute') ? 'active' : '' }}">
    <a href="{{route('yournamedroute')}}">Yournamedroute</a>
</li>
```