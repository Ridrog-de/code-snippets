---
title: 'Use own Packages'
taxonomy:
    category:
        - docs
---

#### Update the package composer file.

Wir müssen dem Packet sagen was es zum autoloaden angeben soll.

```
"autoload": {
        "psr-4": {
            "Vendor\\Name\\": "src/"
        }
    }
```


#### Edit the main composer file

```
"minimum-stability": "dev",
"prefer-stable" : true,
```