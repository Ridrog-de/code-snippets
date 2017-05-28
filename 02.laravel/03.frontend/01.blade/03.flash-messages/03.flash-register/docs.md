---
title: 'Flash Register'
taxonomy:
    category:
        - docs
---

Um nach einem Register eine Flash Message anzuzeigen, müssen wir die Funktion `register` aus den Framework Dateien in unseren AuthController kopieren.  
(laravel/framework/src/Illuminate/Foundation/Auth/RegistersUsers.php)  
  
Und um `session()->flash('success', 'You are now registered and already logged in');` oder was immer man auch machen möchte, erweitern.

Wir müssen auserdem `use Illuminate\Http\Request;` im Kopf des AuthController benutzen.


	public function register(Request $request)
    {
        $validator = $this->validator($request->all());

        if ($validator->fails()) {
            $this->throwValidationException(
                $request, $validator
            );
        }

        Auth::guard($this->getGuard())->login($this->create($request->all()));
        session()->flash('success', 'You are now registered and already logged in');
        return redirect($this->redirectPath());
    }





