---
title: 'Socialite Routes'
taxonomy:
    category:
        - docs
---

Universelle Routen für Socialite

```
/**
 * Socialite
 */
Route::get('/auth/{provider}', 'Auth\SocialiteController@redirectToProvider');
Route::get('/auth/{provider}/callback', 'Auth\SocialiteController@handleProviderCallback');
```


```
/**
 * Socialite
 */
Route::get('/login/{provider}', 'Auth\SocialiteController@redirectToProvider');
Route::get('/login/{provider}/callback', 'Auth\SocialiteController@handleProviderCallback');
```