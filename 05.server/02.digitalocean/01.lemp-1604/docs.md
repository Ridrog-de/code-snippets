---
title: LEMP on Ubuntu 16.04
taxonomy:
    category:
        - docs
    date:
        - 25.05.2017
    update:
        - 26.05.2017
---


Ziel: Einen Server mit dem LEMP Stack installieren.

Git, Composer und was man nicht alles braucht um automatisch zu veröffentlichen
Staging Server, Mehrere Domains ..
Https

## Vorbereitung


4. Secure MySQL???? TODO
    



### Composer installieren


### Laravel installieren

**Laravel Installer**

```
composer global require "laravel/installer"
```

```
cd ~/
nano .profile
```

hinzufügen:

```
export PATH=$PATH:$HOME/.composer/vendor/bin
```

neu verbinden

#### Installieren

in den richtigen Ordner wechslen

```
cd /
cd var/www/html
```

```
laravel new test
```

```
sudo chown -R :www-data /var/www/html/test
```

```
sudo chmod -R 775 /var/www/html/test/storage
sudo chmod -R 775 /var/www/html/test/bootstrap/cache
```

#### Den Root Ordner ändern

```
cd /
cd etc/nginx/sites-enabled
nano digitalocean
```

und da root auf den neuen Ordner ändern

und in server > location folgende Zeile hinzufügen:

```
try_files $uri $uri/ /index.php?$query_string;
```


**Konfiguration prüfen**
```
sudo nginx -t
```

**nginx neu starten**
```
sudo systemctl restart nginx
```


