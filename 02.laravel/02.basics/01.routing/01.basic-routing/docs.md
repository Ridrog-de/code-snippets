---
title: 'Basic Routing'
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
menu: 'Basic'
slug: 'basic'
---

Die einfachste aller Routen akzeptiert eine URI und eine Closure

```
Route::get('foo', function () {
    return 'Hello World';
});
```


## Methoden

```
Route::get($uri, $callback);
Route::post($uri, $callback);
Route::put($uri, $callback);
Route::patch($uri, $callback);
Route::delete($uri, $callback);
Route::options($uri, $callback);
```

## Match

```
Route::match(['get', 'post'], '/', function () {
    //
});
```

## Any

```
Route::any('foo', function () {
    //
});
```

## CSRF Protection

Alle ```POST```, ```PUT``` und ```DELETE``` Routen werden von der CSRF Middleware beschützt.

## CSRF Field Helper

```
    {{ csrf_field() }}
```

```
<input type="hidden" name="_token" value="{{ csrf_token() }}">
```

## Method Spoofing

```
{{ method_field('PUT') }}
```

```
<input type="hidden" name="_method" value="PUT">
```