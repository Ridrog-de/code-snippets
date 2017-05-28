---
title: 'Admin Area'
taxonomy:
    category:
        - docs
---

#### Middleware erstellen  

```
php artisan make:middleware MustBeAdmin
```

#### Middleware füllen

```
public function handle($request, Closure $next)
    {
        $user = $request->user();

        if ($user && $user->role == "admin"){
            return $next($request);
        } else {
            return abort('403');
        }
    }
```

#### Middleware registrieren

in: _app/Http/Kernel.php_ unter: _protected $routeMiddleware_

```
'admin' => \App\Http\Middleware\MustBeAdmin::class
```

#### Seiten per Middleware schützen

_im Controller_

```
public function __construct()
    {
    	$this->middleware('admin');
    }
```
	
    
_in der Route_
```
Route:get('/home', ['middleware' => 'admin', 'uses' => 'XController@x']);
```
	

