---
title: Seeding
taxonomy:
    category:
        - docs
---

Laravel Database: Seeding

**Basics**

Mit Datenbank Seedern kann man Datenbank befüllen.
Mit allen möglichen automatisch generiereten Daten.


Ausführen kann man es mit: 

	php artisan db:seed

Dieser Befl führt nur den einen Seeder aus, der schon vorhanden ist, um aus der Datei heraus mehr auszuführen muss man sie in der Funktion aufrufen:

	$this->call(UsersTableSeeder::class);


Eine bestimmte Datei ausführen mit: 

	php artisan db:seed --class=UsersTableSeeder
    
Es gibt auch einen artisan Befehl

	php artisan make:seeder seederName
    
    
#### Alle Migrations neu und seeden

```
php artisan migrate:refresh --seed
```
    
#### Admin User erstellen

im neu erstellen UsersTableSeeder

```
User::create([
            "name" => "admin",
            "email" => "admin@admin.de",
            "password" => bcrypt('123456'),
            "role" => "admin"
        ]);
```