# Laravel How To

## Installation
- [how to create a project with composer][]
- [how to remove 500 internal server error][]

## Model
- [how to create a model][]
- [how to add your database information][]

## View
- [how to extend a blade layout][extend]

## Controller
- [how to create a controller][]

[home]:#laravel-how-to
[extend]:#how-to-extend-a-blade-layout

### HOW TO EXTEND A BLADE LAYOUT
- create a layout file and make sure you have the yield function that has a name
inside the parentheis
    - example: yield('main')
- create a file that extends that layout file and make you have the extends()
function and the section() function inside of it

**layout.blade.php**

```php
    <html>
        <head>
        </head>
        <body>
            yield('main')
        </body>
    </html>

```
**main.blade.php**

```php
    @extends('layout')
    @section('main')
        <main>
           this is the main content
        </main>
    @stop

```
[go back to home][home]
