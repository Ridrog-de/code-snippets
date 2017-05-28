---
title: Erste Schritte
taxonomy:
    category:
        - docs
    date:
        - 26.05.2017
    update:
        - 26.05.2017
---


### Herunterladen

```
cd ~
curl -sS https://getcomposer.org/installer -o composer-setup.php
```


### Verifizieren

```
php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
```

### Installieren

```
sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
```

### Dateirechte anpassen

Für erste funktioniert das:

```
sudo chmod -R 777 /home/ridrog/.composer
```

TODO: Wie besser machen?