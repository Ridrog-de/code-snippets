---
title: Bootstrap Footer
published: true
date: '28-05-2017 11:24'
publish_date: '28-05-2017 11:24'
taxonomy:
    category:
        - docs
    framework: 
        - bootstrap
menu: Footer
slug: footer
---

Not Sticky, aber immer am unteren Bildrand

```scss
html {
  position: relative;
  min-height: 100%;
}
body {
  margin-bottom: 70px;
}
.footer {
  color: $navbar-default-color;
  background: $navbar-default-bg;
  border-top: 1px solid $navbar-default-border;
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 60px;
}
```
