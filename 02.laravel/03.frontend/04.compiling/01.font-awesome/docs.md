---
title: font-awesome
taxonomy:
    category:
        - docs
---

Font-awesome über npm installiert, mit Elixier in Laravel einbinden

### 1. Installieren

```
npm install font-awesome --save-dev
```

### 2. Die Schriften kopieren
_Einmaliger Schritt, kann danach auskommentiert werden_

```js
function copyFontAwesomeFonts(){
    mix.copy('./node_modules/font-awesome/fonts', './public/fonts');
}
```

### 3. Kompilieren
in der Haupt scss Datei:  
_den Pfad zu den Schriftarten setzen und fontawesome importieren_

```
$fa-font-path: "/fonts";
@import "./node_modules/font-awesome/scss/font-awesome";
```