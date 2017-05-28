---
title: Password Request View
published: true
date: '28-05-2017 11:24'
publish_date: '28-05-2017 11:24'
taxonomy:
    category:
        - docs
menu: Password Request
slug: password-request
---

#### Send an email to reset password with bulma

```blade
    <section class="hero is-bold">

        <div class="hero-body">
            <div class="container">
                <div class="columns is-vcentered">
                    <div class="column is-6 is-offset-3">
                        <h1 class="title">
                            Reset Password
                        </h1>
                        <div class="box">
                            @if (session('status'))
                                <div class="notification is-success">
                                    {{ session('status') }}
                                </div>

                            @endif

                            <form role="form" method="POST" action="{{ url('/password/email') }}">
                                {{ csrf_field() }}

                                <label class="label">Email</label>
                                <p class="control has-icon has-icon-right">
                                    <input class="input" type="email" placeholder="jsmith@example.org" name="email" value="{{ old('email') }}" required autofocus>

                                    @if ($errors->has('email'))
                                        <span class="icon is-small">
                                            <i class="fa fa-warning"></i>
                                        </span>
                                        <span class="help is-danger">{{ $errors->first('email') }}</span>
                                    @endif
                                </p>


                                <p class="control">
                                    <button class="button is-primary" type="submit">Send Password Reset Link</button>
                                </p>

                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>

    </section>
```