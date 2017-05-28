---
title: Laravel Routing
published: true
date: '28-05-2017 11:24'
publish_date: '28-05-2017 11:24'
taxonomy:
    category:
        - docs
    tag:
        - laravel
    language:
        - php
    version:
        - '5.4'
    framework:
        - laravel
menu: Routing
slug: routing
---

Alles zu Laravel's Routing



### Little Helper

Dem Model selbst sagen, wie der Pfad zu ihm ist

```
public function path()
{
    return route('thread-show', ['thread' => $this->id]);
}
```

Dann kann man in seinen Views sagen: 

```
<a href="{{ $model->path() }}">
	{{ $model->title }}
</a>
```