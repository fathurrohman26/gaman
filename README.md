# gaman (in progress)

> `gaman` is a template engine for CodeIgniter version 3 where `gaman` itself is taken from the translation of the word `blade` in Javanese. Because gaman is inspired from Laravel's `Blade`.

### Install

Integrate `gaman` in ci3 application
.....

### Directive

`extends`

```blade
@extends('layouts.base')
```

`include`

```blade
@include('templates.sidebar-left')
```

`includeIf`

```blade
@includeIf($showSidebar === true, 'templates.sidebar')
```

`yield`

```blade
@yield('content')
```

`section`

```blade
@section('title', 'Welcome') <!-- Inline -->

@section('title')
	<title>Welcome | CI 3 </title>
@endsection
```

`stack`

```blade
@stack('css')
```

`push`

```blade
@push('css')
	<style lang="text/sass" id="main-sass">
	</style>
@endpush

@push('css')
	<style lang="text/css" id="main-css">
	</style>
@endpush
```

`echo | escaped`

```blade
{{ $variable }}
```

`echo | unescaped`

```blade
{!! $variable !!}
```

`raw`

```jsx
@{{ name }} // example usage with js
```

`if`

```blade
@if ($user->isAuthenticated())
	<p>Hello, {{ $user->name }}</p>
@endif
```

`if else`

```blade
@if ($user->isAuthenticated())
	<p>Hello, {{ $user->name }}</p>
@else
	<p>You're not logged in</p>
@endif
```

`elif`

```blade
@if ($user->isAuthenticated() and $user->isVerified())
	<p>Hello, {{ $user->name }}</p>
@elif ($user->isAuthenticated() and $user->isUnverified())
	<p>Hello, {{ $user->name }}, please verify your email address.</p>
@else
	<p>You're not logged in</p>
@endif
```

`for`

```blade
for ($i=0; $i<10; $i++)
	{{ $i }}
@endfor
```

`foreach`

```blade
foreach ($users as $user)
	{{ $user->name }}
@endforeach
```

`while`

```blade
$i = 0;

@while ($i <= 100)
	$i += 10;
@endwhile
```

### Function

`asset`

```blade
<link rel="stylesheet" href="{{ asset('themes/ci/default.css') }}>
```
