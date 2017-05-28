---
title: Laravel Testing
published: true
date: '28-05-2017 11:24'
publish_date: '27-05-2017 16:39'
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
menu: Testing
slug: testing
---

1. [Getting Started](start)
2. [HTTP Tests](http)
3. [Browser Tests](browser)
4. [Database](database)
5. [Mocking](mocking)


--------------------

# Tests aufrufen

## PHPStorm einstellen

einfach nur die phpunit file im vendor/phpunit/phpunit angeben und schon kann man aus der IDE herraus Tests starten
 
 
## Konsole

In der Windows Powershell habe ich mir ein Alias angelegt, mit dem ich direkt ```php vendor/phpunit/phpunit/phpunit``` aufrufen.
Leider kann man da (noch) keine weiteren Befelhe mit ausführen,
ab um die gesamte Suite auzuführen reicht das


# Setup

Für einfach Tests ist kein Setup erforderlich.

Um mit Datenbanken zu arbeiten muss man aber die ENV Variabeln für die Datenbank angeben,
damit man auf eine Test-Datenbank zugreifen kann.

_at phpunit.xml_

```
<env name="DB_CONNECTION" value="mysql"/>
<env name="DB_HOST" value="127.0.0.1"/>
<env name="DB_PORT" value="3306"/>
<env name="DB_DATABASE" value="NAME_OF_THE_DATABASE"/>
<env name="DB_USERNAME" value="root"/>
<env name="DB_PASSWORD" value=""/>
```

# Die ersten Tests

Laravel bringt schon ein paar Tests mit.

Die Kommentare, mit dem ```/** @test */``` zu ersetzen, bringt einem die Freiheit,
die Test so zu bennenen wie man gerne möchte.
Ansonsten müssen die funtionen mit "test" anfangen, damit sie aufgerufen werden.
Die Dateien, müssen alle auf "Test.php" enden, damit sie aufgerufen werden.


```
/** @test */
public function this_is_a_basic_test()
{
    $this->assertTrue(true);
}
```



