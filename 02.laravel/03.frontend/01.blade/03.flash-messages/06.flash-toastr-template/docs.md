---
title: 'Flash Toastr Template'
taxonomy:
    category:
        - docs
---

```blade

@if (Session::has('success'))
    <script>
        toastr["success"]("{{ session('success') }}")
    </script>
@endif

@if (Session::has('error'))
    <script>
        toastr["error"]("{{ session('error') }}")
    </script>
@endif

@if (Session::has('danger'))
    <script>
        toastr["error"]("{{ session('danger') }}")
    </script>
@endif

@if (Session::has('info'))
    <script>
        toastr["info"]("{{ session('info') }}")
    </script>
@endif

@if (Session::has('warning'))
    <script>
        toastr["warning"]("{{ session('warning') }}")
    </script>
@endif
```