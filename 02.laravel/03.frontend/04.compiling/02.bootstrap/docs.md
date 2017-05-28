---
title: Bootstrap
taxonomy:
    category:
        - docs
---

### 1. Bootstrap-sass installieren

```
npm install bootstrap-sass --save-dev
```

### 1a. Ein Kopie der Bootstrap Variablen kopieren

```js
function copyBootstrapVaribales(){
    elixir(function(mix) {
        mix.copy('./node_modules/bootstrap-sass/assets/stylesheets/bootstrap/_variables.scss', './resources/assets/sass/bootstrap/_variables.scss');
    });
}
```

### 2. Importieren


```
@import "bootstrap/variables";
@import "./node_modules/bootstrap-sass/assets/stylesheets/bootstrap";
```

### 2a. Bootswatch Themes importieren
davor müssen natürlich die bootswatch themes installiert werden.  
`npm install bootswatch --save-dev`

```
@import "./node_modules/bootswatch/flatly/variables";
@import "./node_modules/bootstrap-sass/assets/stylesheets/bootstrap";
@import "./node_modules/bootswatch/flatly/bootswatch";
```


### 3. Kompilieren
Mit Laravels Elixir

```
mix.sass('app.scss');
```


# Javascript

### 1. Browserify

```
window.$ = window.jQuery = require('jquery')
require('bootstrap-sass');
```
