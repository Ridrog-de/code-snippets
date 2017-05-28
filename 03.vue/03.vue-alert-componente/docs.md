---
title: VUE Alert Component
published: true
date: '27-05-2017 16:52'
publish_date: '27-05-2017 16:52'
taxonomy:
    language:
        - js
    framework:
        - vuejs
menu: Alert Component
slug: alert
---

### Componente

```
<template>
    <div class="alert alert-{{type}} flash-message" role="alert" v-if="display" transition="expand">
        <button type="button" class="close" v-on:click="hide" v-if="this.time === 0">
            &times;
        </button>
        {{message}}
    </div>
</template>

<style>
    .expand-transition {
      transition: all 1s ease;
    }

    .expand-enter, .expand-leave {
      opacity: 0;
    }
</style>

<script>
    export default {
        ready(){
            if (this.time > 0){
                setTimeout(this.hide, this.time);
            }
        },
        props : {
            message: {
              type: String,
              required: true,
            },
            type: {
              default: 'success'
            },
            time: {
                default: 5000
            }
        },
        data : function (){
            return {
                display: true
            }
        },
        methods : {
            hide : function (){
                this.display = false;
            }
        }
    }
</script>

```

### Main JS

```javascript
/* jshint esversion: 6 */

import Vue from 'vue';
import FlashMessage from './components/flash-message.vue';

new Vue({
    el: '#app-layout',

    components: {
        FlashMessage
    },

    ready : function (){
        console.log ("Main Vue Ready");
    }
});

```

### Blade Teilstück

```
<div id="GlobalNotification">
    @if (Session::has('success'))
        <flash-message message="{{ session('success') }}" type="success"></flash-message>
    @endif

    @if (Session::has('danger'))
        <flash-message message="{{ session('danger') }}" type="danger"></flash-message>
    @endif

    @if (Session::has('info'))
        <flash-message message="{{ session('info') }}" type="info"></flash-message>
    @endif

    @if (Session::has('warning'))
        <flash-message message="{{ session('alert') }}" type="alert"></flash-message>
    @endif

    @if (Session::has('critical-error'))
        <flash-message message="{{ session('danger') }}" type="danger" time="0"></flash-message>
    @endif
</div>
```

### SCSS

```
#GlobalNotification{
    position: absolute;
    bottom: 0;
    right: 20px;
    width: 300px;
    z-index: 3000;


    > .alert{
        box-shadow: $box-shadow-3;
    }
}
```

### Benutzen

```
session()->flash('info', 'You are now logged out');
```