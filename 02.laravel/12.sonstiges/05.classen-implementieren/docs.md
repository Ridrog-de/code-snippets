---
title: 'Classen implementieren'
taxonomy:
    category:
        - docs
---

man erstellt eine Klasse, eine Funktion ... was auch immer
dann muss man Composer sagen, das man diese autoloaden will.

Man erweitert dazu die Composer.json Datei

	
    "autoload" : {
    	"classmap" : [.....],
        
        "files" : [
        	"app/helper/helper.php",
        	// Hier kommen alle Pfade zu den Dateien rein
        ],
        "psr-4" : {.....}
    }
    

dann müssen wir noch:

	composer dumpautoload
    
in der Console eingeben