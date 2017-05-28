---
title: Middleware
taxonomy:
    category:
        - docs
---

laravel's middleware

### Auth

Um einen Controller, bzw die Funktionen darin nur für eingeloggt User zugegänglich zu machen, muss man einfach nur dem Kontruktor des Controllers sagen: 

    public function __construct()
    {
    	$this->middleware('auth');
    }

Das ist alles, aber jetzt wird gescheckt ob der User eingeloggt ist.

#### Funktionen ausschließen

	public function __construct()
    {
    	$this->middleware('auth', ['except' => 'nameDFun']);
    }
    
#### Nur auf eine Funktion 

    public function __construct()
    {
    	$this->middleware('auth', ['only' => 'nameDFun']);
    }
    
-----------------------------------

#### Auf der Route

Man kann die Middleware auch direkt in der Route angeben

    Route:get('/home', ['middleware' => 'auth', 'uses' => 'XController@x']);
    
    
-----------------------------------

## Create a new Middleware

    php artisan make:middleware NameOfTheMiddleware
    
Am Ende return eine Middleware immer: 

    return $next($request);

Um zu checken ob ein User ein bestimmtes Atribut hat:
Diese Funktion redirectet wenn es nicht so ist ...

	public function handle ($request, Closure $next)
    {
    	if ( ! $request->user()->isWhatEverYouWanna)
        {
        	return redurect ('somesite');
        }
        
        
    	return $next($request);
    }

