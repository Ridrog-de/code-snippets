---
title: VUE Animation
published: true
date: '27-05-2017 16:52'
publish_date: '27-05-2017 16:52'
taxonomy:
    language:
        - js
    framework:
        - vuejs
menu: Animation
slug: animation
---

Es gibt ein Projekt, das die Animation von [animate.css](https://daneden.github.io/animate.css/) für vue angepasst hat

[vue-animate](https://github.com/haydenbbickerton/vue-animate)

```
npm install vue-animate --save-dev
```

### Das CSS einbinden

```
@import "./node_modules/vue-animate/dist/vue-animate";
```


---------------------------

Da es aber so simpel ist, kann man ganz einfach auch selbst animationen schreiben.

**Beispiel Expand**

```css
.expand-transition {
        transition: all .8s ease;
        max-height: 600px;
        overflow: hidden !important;
    }


    .expand-enter, .expand-leave {
        max-height: 0;

    }

```