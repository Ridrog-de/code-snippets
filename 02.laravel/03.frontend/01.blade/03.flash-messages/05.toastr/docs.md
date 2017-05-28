---
title: 'Flash Toastr'
taxonomy:
    category:
        - docs
---

[Toastr at Github](https://github.com/CodeSeven/toastr)  
[Demo](http://codeseven.github.io/toastr/demo.html)  

-----------------
### Install

```
npm install --save-dev toastr
```


### Require it

```js
window.toastr = require('toastr');
```

### Inculde the css
In der Haupt sass datei

```
@import "./node_modules/toastr/build/toastr";
```


### Setup

```js
toastr.options = {
    "closeButton": true,
    "debug": false,
    "newestOnTop": true,
    "progressBar": true,
    "positionClass": "toast-bottom-right",
    "preventDuplicates": false,
    "onclick": null,
    "showDuration": "300",
    "hideDuration": "1000",
    "timeOut": "6000",
    "extendedTimeOut": "1000",
    "showEasing": "swing",
    "hideEasing": "linear",
    "showMethod": "fadeIn",
    "hideMethod": "fadeOut"
}
```

### Benutzen

```js
	toastr["success"]("Message", "Titel")
```

PHP Version (Laravel)
```php
session()->flash('success', 'You are now logged in');
```

weitere optionen sind: `error`, `info` und `warning`  
Der Titel ist optional