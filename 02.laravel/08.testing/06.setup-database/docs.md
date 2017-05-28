---
title: Setup Test Database
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
menu: Setup Database
slug: setup-database
---

at phpunit.xml

```
<env name="DB_CONNECTION" value="mysql"/>
<env name="DB_HOST" value="127.0.0.1"/>
<env name="DB_PORT" value="3306"/>
<env name="DB_DATABASE" value="NAME_OF_THE_DATABASE"/>
<env name="DB_USERNAME" value="root"/>
<env name="DB_PASSWORD" value=""/>
```

Oder eine eigene Verbindung anlegen und nur diese Verbindung angeben

```
<env name="DB_CONNECTION" value="mysql_test"/>
```