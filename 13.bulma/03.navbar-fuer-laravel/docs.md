---
title: Navbar für Laravel
published: true
date: '28-05-2017 11:24'
publish_date: '28-05-2017 11:24'
taxonomy:
    category:
        - docs
menu: Laravel Navbar
slug: laravel-navbar
---

#### Bulma Navbar für Laravel

```html
<nav class="nav has-shadow">
    <div class="container">
        <div class="nav-left">
            <a href="{{ route('welcome') }}" class="nav-item is-tab {{ Route::is('welcome') ? 'is-active' : '' }}">
               <b>{{ config('app.name') }}</b>
            </a>


            @if (Auth::guest())

            @else
                <a href="{{ route('home') }}" class="nav-item is-tab is-hidden-mobile {{ Route::is('home') ? 'is-active' : '' }}">Home</a>
            @endif

        </div>
        <span class="nav-toggle">
      <span></span>
      <span></span>
      <span></span>
    </span>
        <div class="nav-right nav-menu">
            @if (Auth::guest())

                <a href="{{ route('login') }}" class="nav-item is-tab {{ Route::is('login') ? 'is-active' : '' }}">
                    Login
                </a>

                <a href="{{ route('register') }}"class="nav-item is-tab {{ Route::is('register') ? 'is-active' : '' }}">
                    Register
                </a>

            @else
                <a href="{{ route('home') }}" class="nav-item is-tab is-hidden-tablet {{ Route::is('home') ? 'is-active' : '' }}">Home</a>

                <a class="nav-item is-tab">
                    {{ Auth::user()->name }}
                </a>


                <a href="{{ route('logout') }}" class="nav-item is-tab" onclick="event.preventDefault(); document.getElementById('logout-form').submit();">
                    Log out
                </a>

                <form id="logout-form" action="{{ route('logout') }}" method="POST" style="display: none;">
                    {{ csrf_field() }}
                </form>
            @endif

        </div>
    </div>
</nav>


```