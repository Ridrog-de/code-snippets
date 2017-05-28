---
title: 'API Token'
taxonomy:
    category:
        - docs
---

#### Ein API Token beim registrieren erstellen

_Http/Controller/Auth/RegisterController.php_

in der Funktion "create" einfach ein random string erzeugen

```
'private_api_token' => str_random(60),
```

Den gewählten Namen für den Token im User-Model als $fillable and eventuell auch noch als $hidden eintragen

Die Migration anpassen und ```php artisan migrate:refresh```