---
title: Getting Started
taxonomy:
    category:
        - docs
---

Laravel Eloquent ORM: Getting Started


## Erstellen

	php artisan make:model Modelname

### Mit Datenbank

```
php artisan make:model Modelname -m
```

### Mit Datenbank und Resource Controller

```
php artisan make:model -mr MODELNAME
```

## Daten für Mass Assignment freigeben
einfach ein Array mit allen Feldern machen, die man auf einmal ausfüllen kann.

	protected $fillable = [
        'title', 
        'body',
        'whatever'
    ];

## Versteckte Felder

	protected $hidden = [
        'password', 
        'email'
    ];
    


## Scopes
für häufig genutzte Abfragen

    public function scopeDerName ($query, $eineVariable)
    {
        $query->where('EinAttribut', 'erfülltBedinung');
    }

#### den Scope nutzen

	MeinModel::DerName($eineVariable);
    

## Mutator
Wenn ein Attribut gesetzt wird, dann soll Laravel es anpassen. Wichtig ist der Name der Funktion, erst "set", dann der Name und dann noch "Attribute"

    public function setWasAttribute($variable)
    {
        $this->attributes["WelchesAtrribut"] = Carbon::parse($date);
    }

In diesem Codesnippet wird immer wenn das Attribut gesetzt wird, eine Carbon Funktion aufgerufen um ein Datum in eine Carbon Instanz umzuwandeln.

Das ist auch nützlich um Passwörter zu Speichern.


	$this->attributes["password"] = mcrypt($password);


## Boot

Man kann Funktionen automatisch, beim aufrufen, instanzieren eines Models, ausführen lassen. Bzw auch bei anderen Aktionen, wenn ein neues Model erstellt wird, oder wenn es upgedated wird ....

    public static function boot()
    {
        parent::boot();

        static::creating(function($user){
            $user->token = str_random(30);
        });
    }
    
    
Mit dieser Funktion, erstellen wir, wenn ein Model erstellt wird, einen random string den wir dem Model unter token hinzufügen.