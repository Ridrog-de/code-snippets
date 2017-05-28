---
title: 'Active Page'
taxonomy:
    category:
        - docs
---

#### Mit benannten Routen

```
<li class="{{ Route::is('nameDerRoute') ? 'is-active' : '' }}">
    <a href="{{ route('nameDerRoute') }}">
        Advanced
    </a>
</li>
```

#### Gruppen
todo

Wie mache ich das für Gruppen um z.B. ein Dropdown active zu setzen?


---------------------

Die active Class setzten, oder auch andere Klassen
Hier im Beispiel, die active Class des Bootstraps, über Laravels Blade 

    <li 
    	class="{{ $activePage == 'kontakt' ? 'active' : '' }}">
        	<a href="{{ url('/kontakt') }}">Kontakt</a>
    </li>
    
Natürlich muss dazu noch die aktive Seite im Controller oder im Router übergeben werden

    public function home() {
        return view('pages/home')->with('activePage', 'home');
    }
    
    
Um Fehler zu vermeiden wenn keine Aktive Seite übergeben wird:  
_im Blade Template_  

```
@if( ! isset($activePage))
    {{ $activePage = "" }}
@endif
```