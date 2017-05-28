---
title: 'Flash Login'
taxonomy:
    category:
        - docs
---

Um nach einem Login eine Flash Message anzuzeigen, müssen wir die Funktion `authenticated` aus den Framework Dateien in unseren AuthController kopieren.  
(laravel/framework/src/Illuminate/Foundation/Auth/AuthenticatesUsers.php)  
  
Und um `session()->flash('success', 'You are now logged in');` oder was immer man auch machen möchte, erweitern.


	public function authenticated( \Illuminate\Http\Request $request, \App\User $user )
    {
        session()->flash('success', 'You are now logged in');
        return redirect()->intended($this->redirectPath());
    }





