---
title: 'Flash Messages'
taxonomy:
    category:
        - docs
---

Flash Messages in laravel 

Wenn man nach einer Aktion redirected wird. Z.B. Login, logout, etwas erstellt ....
  
**Die Nachricht übergeben**  

    session()->flash('nameDerNachricht', 'Die Nachricht');
    
    
**Die Nachricht abfangen**

_in der(Blade) View_

	@if (Session::has('nameDerNachricht'))
      	{{ session('nameDerNachricht') }}
    @endif


Um es auszublenden muss man mit Javascript arbeiten