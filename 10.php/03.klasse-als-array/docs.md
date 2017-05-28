---
title: PHP Klasse als array
published: true
date: '28-05-2017 13:40'
publish_date: '28-05-2017 13:40'
taxonomy:
    category:
        - docs
    language:
        - php
    tag:
        - php
menu: Strings
slug: strings
---

Ziel ist es auf eine Klasse genauso zuzugreifen wie auf ein Array.


```php
<?php

class Message implements ArrayAccess
{
    public $title = "Hello World";
    
    public function offsetExists($offset) 
    {
        return isset($this->$offset);
    }
    
    public function offsetGet($offset)
    {
        return $this->$offset;
    }
    
    public function offsetSet($offset, $value)
    {
        $this->$offset = $value;
    }
    
    public function offsetUnset($offset)
    {
        unset($this->$offset);
    }
}

// Beispiel

$message = new Message();
echo $message["title"];

```
