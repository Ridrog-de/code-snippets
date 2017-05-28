---
title: Getting Started
taxonomy:
    category:
        - docs
---

Laravel Database: Getting Started


! Es besteht ein kleiner Konflikt, wenn man Laravel 5.4 und eine ältere Datenbank nimmt.  
! Dann erscheint bei ```php artisan migrate``` folgender Fehler:  
! _....Specified key was too long ..._  
! Um diesen zu fixen muss man einfach in _app/Providers/AppServiceProvider.php_ folgende Änderung machen

```
use Illuminate\Support\Facades\Schema;

public function boot()
{
    Schema::defaultStringLength(191);
}
```