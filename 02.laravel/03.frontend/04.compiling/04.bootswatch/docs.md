---
title: Bootswatch
taxonomy:
    category:
        - docs
---

#### Install

```
npm install --save-dev bootswatch
```


## Kopiere ein einzelnes Bootswatch Theme

_in dem gulfile_
```
function copyBootsWachSingle(theme){
    mix.copy('./node_modules/bootswatch/'+ theme +'/_variables.scss', './resources/assets/sass/themes/'+theme+'/_variables.scss');
    mix.copy('./node_modules/bootswatch/'+ theme +'/_bootswatch.scss', './resources/assets/sass/themes/'+theme+'/_bootswatch.scss');
}
```

_in der app.scss_
```
// Bootstrap with bootswatch theme
@import "themes/flatly/variables";
@import "node_modules/bootstrap-sass/assets/stylesheets/bootstrap";
@import "themes/flatly/bootswatch";
```

## Verschiedene Themes erstellen.
_am Beispiel von bootswatch_

#### Themes definieren
alle gewünschten Themen in der variablen themes definieren oder einfach alle referenzieren.

```
var allThemes = ['cerulean', 'cosmo', 'cyborg', 'darkly', 'flatly', 'journal', 'lumen', 'paper', 'readable', 'sandstone', 'simplex', 'slate', 'spacelab', 'superhero', 'united', 'yeti'];
var themes = allThemes; // or an array with the choosen themes
```

#### Alles kopieren

Eine Vorlage erstellen, wie die Themes kompiliert werden sollen und diese dann in die Ordner der Themes kopieren.  
theme.template.scss
```
@import "variables";
@import "node_modules/bootstrap-sass/assets/stylesheets/bootstrap";
@import "bootswatch";
```


Diese Funktion wird einmalig aufgerufen, sie kopiert alle nötigen Dateien in resources/assets/sass/themes und ein Thumbnail in den public Ordner  
_im gulpfile_  
**nach dem einmaligen ausführen wieder auskommentieren, da man sich sonst alle variablen wieder überschreibt**

```
copyMultipleBootswatch(themes);
```

```
function copyMultipleBootswatch(themes){

   for (var i = 0; i < themes.length; i++) {
        elixir(function(mix) {
            mix.copy('./node_modules/bootswatch/'+ themes[i] +'/_variables.scss', './resources/assets/sass/themes/'+themes[i]+'/_variables.scss');
            mix.copy('./node_modules/bootswatch/'+ themes[i] +'/_bootswatch.scss', './resources/assets/sass/themes/'+themes[i]+'/_bootswatch.scss');
            mix.copy('./node_modules/bootswatch/'+ themes[i] +'/thumbnail.png', './public/themes/'+themes[i]+'.png');
            mix.copy('./resources/assets/sass/theme.template.scss', './resources/assets/sass/themes/'+themes[i]+'/master.scss');
        });
    }
}
```

#### Alle Themes kompilieren

Diese Funktion ruft man immer dann auf, wenn man Änderungen an den Themes macht
```
copyMultipleBootswatch(themes);
```



```
function compileMultipleBootswatch(themes){
    for (var i = 0; i < themes.length; i++) {
        elixir(function(mix) {
            mix.sass('themes/'+ themes[i] +'/master.scss', './public/themes/'+themes[i]+'.css');
        });
    }
}
```
