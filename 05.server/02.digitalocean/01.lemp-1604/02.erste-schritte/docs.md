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

Als Root einloggen

## Updaten

``` sudo apt-get update ```

## Dependencies installieren

 ``` sudo apt-get install php7.0-mbstring curl php7.0-cgi git unzip php-xml php7.0-zip```

- php7.0-mbstring
- php7.0-cgi
- php-xml
- php7.0-zip
- curl
- git
- unzip

## User anlegen

```
sudo adduser ridrog
```

Passwort vergeben, rest kann leer bleiben

**ridrog zum admin machen**

```
usermod -aG admin ridrog
```

**Benutzer wechseln**
```
sudo su ridrog
```

**SSH Key zum neuen User kopieren**
```
cd ~
mkdir .ssh
nano .ssh/authorized_keys
```

Testen ob ridrog nun sudo Rechte hat.

**Den root zugriff deaktivieren**
```
cd /etc/ssh/
sudo nano sshd_config
```

in der Datei 'PermitRootLogin' auf 'no'

**SSH neu starten**

```
sudo service ssh restart
```

