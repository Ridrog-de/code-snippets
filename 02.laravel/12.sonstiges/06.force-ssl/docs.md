---
title: 'Force SSL'
date: '07-01-2017 23:39'
taxonomy:
    category:
        - docs
---

in _app/providers/AppServiceProvider_ in der "register" Function

```
$this->app['request']->server->set('HTTPS', true);
```