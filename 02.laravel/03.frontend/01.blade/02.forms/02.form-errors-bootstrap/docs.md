---
title: 'Form Errors Bootstrap'
---

Man kann sich die Fehlermeldungen der Validation ganz einfach und schick mit Bootstrap Elementen anzeigen lassen

1. Das div mit der Klasse "form-group" braucht eine Klasse "has-error"  
2. Unter den Input kommt ein span mit der Klasse "help-block"

```
<div class="form-group {{ $errors->has('name') ? ' has-error' : '' }}">
    <label for="name">Name</label>
    <input type="text" class="form-control" id="name" name="name" placeholder="name of the map" value="{{old('name')}}">
	@if ($errors->has('name'))
        <span class="help-block">
			<strong>{{ $errors->first('name') }}</strong>
		</span>
	@endif
</div>
```