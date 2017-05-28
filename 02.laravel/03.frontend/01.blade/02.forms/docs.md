---
title: Forms
taxonomy:
    category:
        - docs
---

laravel forms

### CSFR Token

	{!! csrf_field() !!}

### Methode ändern

	<input type="hidden" name="_method" value="DELETE">


**HTML Service Provider ist nicht mehr länger teil des Core**  


### install illuminate/html  
  
_ein Grundgerüst für html und forms_  

_per Console_  
  
    composer require illuminate/html

### register illuminate/html

_in config > app.php > providers_


    Illuminate\Html\HtmlServiceProvider::class,
    
**die alliase registrieren**  

_in config > app.php > aliases  

    'Form' => Illuminate\Html\FormFacade::class,
    'Html' => Illuminate\Html\HtmlFacade::class,


### benutzen

**Form erstellen**  
  
    {!! Form::open() !!}
    
    {!! Form::close() !!}

**Form füllen**  

    {!! form::label ('name', 'Name') !!}
    {!! form::text ('name', null, ['class' => 'form-control']) !!}
    
    {!! form::textarea ('schreibwas', null, ['class' => 'form-control']) !!}
  
   
Der erste Parameter ist der name, der Zeite der default Wert und im dritten kann man alle möglichen Klassen, Ids oder custom data attributes vergeben.

**Submit Button**  
  
    {!! form::submit ('Submit it!', ['class' => 'btn btn-primary form-control']) !!}
  
