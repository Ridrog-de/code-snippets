---
title: JWTAuth
taxonomy:
    category:
        - docs
---

  
[Github JWT-Auth](https://github.com/tymondesigns/jwt-auth)  
  

#### Installation

	"require": {
    	"tymon/jwt-auth": "0.5.*"
	}
    
Danach `composer update` in der Konsole

**Service Provider**
config->app.php
	
    Tymon\JWTAuth\Providers\JWTAuthServiceProvider::class,
	
    
**Aliases**
config->app.php

	'JWTAuth' => Tymon\JWTAuth\Facades\JWTAuth::class,
    'JWTFactory' => Tymon\JWTAuth\Facades\JWTFactory::class
    

**Konsole**

	php artisan vendor:publish --provider="Tymon\JWTAuth\Providers\JWTAuthServiceProvider"
    
**Key Generieren**

	php artisan jwt:generate
    
### Setup


