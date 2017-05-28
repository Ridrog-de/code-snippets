---
title: Javscript Toastr Plugin
published: true
date: '28-05-2017 11:24'
publish_date: '28-05-2017 11:24'
taxonomy:
    category:
        - docs
    language:
        - javascript
        - js
menu: Toastr
slug: toastr
---

[Beispiele](http://codeseven.github.io/toastr/demo.html)  

Im Gegensatz zu anderen Toast Plugins kann dieses einmal konfiguriert werden und sieht / verhält sich immer gleich.

### Installieren

```
npm install toastr --save-dev
```

### Requiren

```js
window.toastr = require('toastr');
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
    "hideEasing": "easeOutBounce",
    "showMethod": "fadeIn",
    "hideMethod": "fadeOut"
}
```

### Verwenden

```js
	toastr["success"]("Message", "Titel")
```

weitere optionen sind: error, info und warning  
Der Titel ist optional