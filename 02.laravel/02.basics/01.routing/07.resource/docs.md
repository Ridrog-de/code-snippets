---
title: Resource
taxonomy:
    category:
        - docs
---

**Create Resourcefull Controller**

````
php artisan make:controller PostsController -r
````

**Die Routen**

```
Route::resource('posts', 'PostsController');
```

**Alle generierten Routen**

| Method    | URI                    | Name             | Action                                          | Middleware   |                                                                   
| --------- | ---------------------- | ---------------- | ----------------------------------------------- | ------------ |
| GET       | posts                  | posts.index      | App\Http\Controllers\PostsController@index      | web          |
| POST      | posts                  | posts.store      | App\Http\Controllers\PostsController@store      | web          |
| GET       | posts/create           | posts.create     | App\Http\Controllers\PostsController@create     | web          |
| GET       | posts/{post}           | posts.show       | App\Http\Controllers\PostsController@show       | web          |
| PUT       | posts/{post}           | posts.update     | App\Http\Controllers\PostsController@update     | web          |
| DELETE    | posts/{post}           | posts.destroy    | App\Http\Controllers\PostsController@destroy    | web          |
| GET       | posts/{post}/edit      | posts.edit       | App\Http\Controllers\PostsController@edit       | web          |
