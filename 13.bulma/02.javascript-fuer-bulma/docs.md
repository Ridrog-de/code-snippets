---
title: Javascript für Bulma
published: true
date: '28-05-2017 11:24'
publish_date: '28-05-2017 11:24'
taxonomy:
    category:
        - docs
menu: Javascript
slug: javascript
---

#### Das Nav Menü ein und ausblenden

```js
(function() {
    var burger = document.querySelector('.nav-toggle');
    var menu = document.querySelector('.nav-menu');
    burger.addEventListener('click', function() {
        burger.classList.toggle('is-active');
        menu.classList.toggle('is-active');
    });
})();
```