# Security with Laravel

## Authentication

[how to create a simple auth][auth]

[how to redirect after login][redirect]

## API Authentication

[redirect]:#how-to-redirect
[auth]:#how-to-create-a-simple-auth
[home]:#security-with-laravel

### how to redirect after login
In the **LoginController, RegisterController, and ResetPasswordController**
add the property `protected redirectTo = "\"`  to whatever you want

```php
<?php
class LoginController extends Controller
{

    use AuthenticatesUsers;

// this is where you change the redirect
    protected $redirectTo = '/home';

    public function __construct()
    {
        $this->middleware('guest')->except('logout');
    }
}


```

[go back home][home]

### how to create a simple auth

1. in the terminal

`php artisan make:auth`

this will create different views in **resources/views/** with several new folders called
**auth**, **layouts**, and **auth/passwords**. Here are the different blade templates that have been
created.

- login
- app
- register
- email
- reset

2. migrate tables

There are some customized schemas that need to be migrated into the database. If you have
not added your database information yet, you need to go to the **.env** file to add it in
so that it will work

`php artisan make:migrate`

this will create the tables in the specified database

3. that is pretty much it for now

[go back home][home]
