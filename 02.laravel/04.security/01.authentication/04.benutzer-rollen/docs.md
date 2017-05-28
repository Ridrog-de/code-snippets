---
title: 'Benutzer Rollen'
taxonomy:
    category:
        - docs
---

### AuthServiceProvider erweitern

```php
<?php

namespace App\Providers;
//use \Policies\RolePolicy;
use Illuminate\Contracts\Auth\Access\Gate as GateContract;
use Illuminate\Foundation\Support\Providers\AuthServiceProvider as ServiceProvider;

class AuthServiceProvider extends ServiceProvider
{
    /**
     * The policy mappings for the application.
     *
     * @var array
     */
    protected $policies = [
        'App\Model' => 'App\Policies\ModelPolicy',
    ];

    /**
     * Register any application authentication / authorization services.
     *
     * @param  \Illuminate\Contracts\Auth\Access\Gate  $gate
     * @return void
     */
    public function boot(GateContract $gate)
    {
        $this->registerPolicies($gate);

        $gate->define('admin-access', function($user){
            return $user->role == 'admin';
        });

        $gate->define('manager-access', function($user){
            return $user->role == 'manager';
        });

        $gate->define('customer-access', function($user){
            return $user->role == 'customer';
        });
    }
}
```

### Middleware erstellen

```php
<?php

namespace App\Http\Middleware;

use Closure;

class Role
{
   
    public function handle($request, Closure $next, $role)
    {
        if (\Auth::user()->can($role . '-access')) {
          return $next($request);
        }
        
        return response('blank', 404);
    }
}
```

### In der View

```
@can('admin-access')
//
@endcan
```