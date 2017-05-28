---
title: 'Master View Template'
taxonomy:
    category:
        - docs
---

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    @yield('meta')

    <!-- Fonts -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.5.0/css/font-awesome.min.css" integrity="sha384-XdYbMnZ/QjLh6iI4ogqCTaIjrFk87ip+ekIjefZch0Y+PvJ8CDYtEs1ipDmPorQ+" crossorigin="anonymous">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Lato:100,300,400,700">

    <!-- Styles -->
    <link href="{{ elixir('css/all.css') }}" rel="stylesheet">

</head>
<body id="app-layout">
    @include('layouts.app.navbar')

    @include('_partials.flash')

    @yield('content')

    @include('layouts.app.footer')

    <!-- JavaScripts -->
    <script src="{{ elixir('js/all.js') }}"></script>

    @yield('script')
</body>
</html>

```