---
title: 'Flash Logout'
taxonomy:
    category:
        - docs
---

Um nach einem Logout eine Flash Message anzuzeigen, müssen wir die Funktion `logout` aus den Framework Dateien in unseren AuthController kopieren.  
(laravel/framework/src/Illuminate/Foundation/Auth/AuthenticatesUsers.php)  
  
Und um `session()->flash('info', 'You are now logged out');` oder was immer man auch machen möchte, erweitern.

Wir müssen auserdem `use Auth;` im Kopf des AuthController benutzen.


	public function logout()
    {
        Auth::guard($this->getGuard())->logout();
        session()->flash('info', 'You are now logged out');
        return redirect(property_exists($this, 'redirectAfterLogout') ? $this->redirectAfterLogout : '/');
    }





