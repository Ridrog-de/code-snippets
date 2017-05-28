---
title: Queues
taxonomy:
    category:
        - docs
---

Laravel Digging Deeper: Queues

#### Datenbank Queue/ Worker

Datenbanken erstellen

```
php artisan queue:table
```

+

```
php artisan migrate
```

**Starten** 
```
php artisan queue:work
```


#### Events mit Queue

einfach diesen Contract einbinden  

```
implements ShouldQueue
```