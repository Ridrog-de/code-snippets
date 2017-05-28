---
title: 'Login mit Username'
taxonomy:
    category:
        - docs
---

Laravel bietet von Haus aus die Möglichkeit, des einloggens mit username anstatt email. Ein paar kleine Anpassungen an dem von Hause aus mitgelieferten Auth (```php artisan make:auth```) und schon klappt es.

Zuerst: ```php artisan make:auth```

Im ersten Schritt überschreiben wir eine Funktion. Die Funktion "username" gibt standard mässig "email" zurück. Wir wollen aber das beim einloggen der Username verwendet wird.
Im zweiten Schritt sorgen wir dafür das wir beim registrieren auch den Username validieren und anschließend speichern.
Im dritten Schritt erstellen wir ein Feld für den Usernamen in der Datenbank.
Im Schritt 4 und 5 bearbeiten wir die Formulare zum Registrieren und einloggen.
Im 6 Schritt müssen wir noch unsere Layout anpassen, damit da auch der username angezeigt wird.

Zum Schluss müssen wir noch die Datenbank erstellen mit: ```php artisan migrate```

#### 1. Username anstatt email
_app/Http/Auth/LoginController.php_

```
public function username()
{
    return 'username';
}
```

#### 2. Die Registrierung bearbeiten
_app/Http/Auth/RegisterController.php_

bei der Registrierung eines neuen Benutzers müssen wir nun diesen usernamen speichern.

```
protected function validator(array $data)
    {
        return Validator::make($data, [
            'username' => 'required|max:60|unique:users',
            'email' => 'email|max:255',
            'password' => 'required|min:6|confirmed',
        ]);
    }
```

und 

```
protected function create(array $data)
    {
        return User::create([
            'username' => $data['username'],
            'email' => $data['email'],
            'password' => bcrypt($data['password']),
        ]);
    }
```

#### 3. Die Migration bearbeiten
_database/migrations/xxxxxx_create_users_table.php_

```
public function up()
    {
        Schema::create('users', function (Blueprint $table) {
            $table->increments('id');
            $table->string('username', 60)->unique();
            $table->string('email');
            $table->string('password');
            $table->rememberToken();
            $table->timestamps();
        });
    }
```

#### 4. Login View
_resources/views/auth/login.blade.php_

hier ändern wir das Formular Feld das vorher die Email war in Username.

```
<div class="form-group{{ $errors->has('username') ? ' has-error' : '' }}">
    <label for="username" class="col-md-4 control-label">Username</label>

    <div class="col-md-6">
        <input id="username" type="text" class="form-control" name="username" value="{{ old('username') }}" autofocus>
        
        @if ($errors->has('username'))
            <span class="help-block">
                <strong>{{ $errors->first('username') }}</strong>
            </span>
        @endif
    </div>
</div>
```

#### 5. Register View
_resources/views/auth/register.blade.php_

Hier ändern wir das Feld das vorher der Name war in Username

```
<div class="form-group{{ $errors->has('username') ? ' has-error' : '' }}">
    <label for="name" class="col-md-4 control-label">Username</label>

        <div class="col-md-6">
            <input id="username" type="text" class="form-control" name="username" value="{{ old('username') }}" autofocus>

        @if ($errors->has('username'))
            <span class="help-block">
                <strong>{{ $errors->first('username') }}</strong>
            </span>
        @endif
    </div>
</div>
```

#### 6. Layout
_resources/views/layouts/app.blade.php_

hier müssen wir nur "name" in "username" umändern, damit im Header auch was angezeigt wird, in dem Dropdown zum ausloggen.

```
<a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-expanded="false">
    {{ Auth::user()->username }} <span class="caret"></span>
</a>
```

