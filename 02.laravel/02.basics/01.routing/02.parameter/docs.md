---
title: 'Route Parameter'
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
menu: 'Parameter'
slug: 'parameter'
---

## Benötigte Parameter

```
Route::get('user/{id}', function ($id) {
    return 'User '.$id;
});
```

Mehrere Parameter

```
Route::get('posts/{post}/comments/{comment}', function ($postId, $commentId) {
    //
});
```

**Keine '-' sind erlaubt, nur '_'**


## Optionale Parameter

```
Route::get('user/{name?}', function ($name = null) {
    return $name;
});
```

Optionaler Parameter mit Standard Wert
```
Route::get('user/{name?}', function ($name = 'John') {
    return $name;
});
```

