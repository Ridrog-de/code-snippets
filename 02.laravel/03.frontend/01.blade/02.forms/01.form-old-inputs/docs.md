---
title: 'Form Old Inputs'
taxonomy:
    category:
        - docs
---

Man kann den "alten" Inhalt eines Formulars, das an der validation scheitert, mit einer einfachen Funktion wieder anzeigen. 

```php
{{ old('name_des_Feldes')}}
```

Für Select Menüs kann man einen einfachen Check machen

```blade
<select class="form-control" name="select_menu">
    <option value="Option1" @if(old('select_menu') == "Option1") selected @endif >Option1</option>
    <option value="Option2" @if(old('select_menu') == "Option2") selected @endif >Option2</option>
</select>
```