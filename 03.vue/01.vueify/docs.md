---
title: VUEify
published: true
date: '27-05-2017 16:52'
publish_date: '27-05-2017 16:52'
taxonomy:
    language:
        - js
    framework:
        - vuejs
menu: Vueify
slug: vueify
---

#### Installieren

```
npm install --save-dev laravel-elixir-vueify
```

Danach im gulpfile laden

```
require('laravel-elixir-vueify');
```

Jetzt muss man nur noch browserify im Elixier aufrufen und es verwandelt .vue dateien in nutzbar js dateien.


--------------------
#### Haupt js Datei

Dann wird eine main .js datei erstellt, diese läd alles nötige.


```javascript
import Vue from 'vue';
import HomeView from './components/HomeView.vue';

new Vue({
    el: 'body',

    components: {
        HomeView
    }
});
```

Wir importieren die hauptvue datei. Das sollte durch npm automische funktionieren. Danach die Komponente "HomeView" und danach erstellen wir unsere Hauptvue und registrieren die Komponente.

-------------------

#### Komponente
```
<script>
    export default {
        created(){
            alert ("Hello World");
        }
    }
</script>
```

--------------
#### View
```html
<home-view></home-view>
```
oder
```html
<component is="home-view"></component>
```

#### Komponente mit Style und Template (.vue)

```
<template>
	<h1 class="vue-heading"><slot></slot></h1>
</template>

<style>
	.vue-heading{
    	color: red;
    }
</style>

<script>
	export default {
        created(){
            alert ("Hello World");
        }
    }
</script>
```
