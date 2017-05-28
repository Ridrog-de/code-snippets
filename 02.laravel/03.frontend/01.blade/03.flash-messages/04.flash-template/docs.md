---
title: 'Flash Template'
taxonomy:
    category:
        - docs
---

```html
<div id="GlobalNotification">
    @if (Session::has('success'))
        <div class="alert alert-success" role="alert">
            <button type="button" class="close" data-dismiss="alert" aria-label="Close">
                <span aria-hidden="true">&times;</span>
            </button>
            {{ session('success') }}
        </div>
    @endif

    @if (Session::has('danger'))
        <div class="alert alert-danger" role="alert">
            <button type="button" class="close" data-dismiss="alert" aria-label="Close">
                <span aria-hidden="true">&times;</span>
            </button>
            {{ session('danger') }}
        </div>
    @endif

    @if (Session::has('info'))
        <div class="alert alert-info" role="alert">
            <button type="button" class="close" data-dismiss="alert" aria-label="Close">
                <span aria-hidden="true">&times;</span>
            </button>
            {{ session('info') }}
        </div>
    @endif

    @if (Session::has('warning'))
        <div class="alert alert-warning" role="alert">
            <button type="button" class="close" data-dismiss="alert" aria-label="Close">
                <span aria-hidden="true">&times;</span>
            </button>
            {{ session('warning') }}
        </div>
    @endif
</div>

```

### SCSS

```scss
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
