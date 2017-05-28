---
title: 'request erweitern'
taxonomy:
    category:
        - docs
---

### Möglichkeit 1	
    
    $request->request->add(['key' => 'value']);
    
### Möglichkeit 2

	$arr = ['user'=> 'Elegant'];    // ['key' => 'value']
    $data = array_merge($request::all(), $arr);
    
### Möglichkeite 3

	$request->all() + [ "elem1" => "value1", "elem2" => "value2" ];