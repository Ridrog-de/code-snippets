---
title: Carbon
taxonomy:
    category:
        - docs
---

_include_

    use Carbon/Carbon;

**Timestamp**  
 
    Carbon::now()
    
Gibt das aktuelle Datum als timestamp


**xxx ago ** or **in xxx**  

    ->diffForHumans();
    
    
**ein Date als Carbon verwenden**  

_im Model_

    protected $dates = ['name_of_the_date_field'];
    