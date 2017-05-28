---
title: Gruppen
taxonomy:
    category:
        - docs
---

Route Gruppen

```
Route::group([], function(){
    //
});
```

## Alle

```
Route::group(['middleware' => 'auth', 'namespace' => 'Admin', 'prefix' => 'admin'], function () {
    Route::get('/', function ()    {
        // Uses Auth Middleware
    });
});
```

## Middleware

```
Route::group(['middleware' => 'auth'], function () {
    Route::get('/', function ()    {
        // Uses Auth Middleware
    });
});
```

## Namespace

```
Route::group(['namespace' => 'Admin'], function () {
    // Controllers Within The "App\Http\Controllers\Admin" Namespace
});
```

## Sub-Domains

```
Route::group(['domain' => '{account}.myapp.com'], function () {
    Route::get('user/{id}', function ($account, $id) {
        //
    });
});
```

## Prefixes

```
Route::group(['prefix' => 'admin'], function () {
    Route::get('users', function ()    {
        // Matches The "/admin/users" URL
    });
});
```

## Mit Platzhalter im Prefix

    Route::group(['prefix' => 'accounts/{account_id}'], function () {
        Route::get('detail', function ($accountId)    {
            // Matches The "/accounts/{account_id}/detail" URL
    });