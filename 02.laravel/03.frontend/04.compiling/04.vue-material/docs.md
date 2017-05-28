---
title: vue-material
taxonomy:
    category:
        - docs
---

#### Install

```
npm install --save-dev vue-material
```


#### Bootstrap.js
```
const Vue = window.Vue = require('vue');
const VueMaterial = require('vue-material');
const VueResource = require('vue-resource');

Vue.use(VueMaterial.default);
Vue.use(VueResource);
```

#### Master SCSS File
```
// Vue Material
@import "node_modules/vue-material/dist/vue-material";
```
