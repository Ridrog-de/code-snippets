---
title: Gravatar
---

[Github Repo](https://github.com/creativeorange/gravatar)

### Installieren

```
composer require creativeorange/gravatar ~1.0
```

 
```
Creativeorange\Gravatar\GravatarServiceProvider::class,
```

 
```
'Gravatar' => Creativeorange\Gravatar\Facades\Gravatar::class,
```

### Benutzen

In einer Blade View - gibt die URL des Avatar zurück
```
{{ Gravatar::get(Auth::user()->email) }}
```

diese URL muss man noch in ein ```<img>``` tag packen und stylen.
```
<img src="{{ Gravatar::get(Auth::user()->email) }}" class="img-circle" style="height: 40px; margin: 0 5px 0 0; padding: 0;">
```

Um es in einer Navbar zu verweden:
```
.dropdown-toggle_withImage{
	padding-top: 10px !important;
	padding-bottom: 10px !important;
}
```