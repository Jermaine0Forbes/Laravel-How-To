# Security with Laravel

## Authentication

- [how to create multiple authentication][multi-auth]

- [how to create a simple auth][auth]

- [how to redirect after login][redirect]

- [how to change route redirection when trying to login][route-redirection]



## API Authentication

[route-redirection]:#how-to-change-route-redirection-when-trying-to-login
[multi-auth]:#how-to-create-multiple-authentication
[redirect]:#how-to-redirect-after-login
[auth]:#how-to-create-a-simple-auth
[home]:#security-with-laravel




### how to change route redirection when trying to login 

if you are trying to login as an admin, but you keep getting redirected to 
the typical user login route. This is how you change it.

**reference**
- [ Change /login auth redirection](https://laracasts.com/discuss/channels/laravel/laravel-53-change-login-auth-redirection)

**In app/Exceptions/Handler.php**
```php

protected function unauthenticated($request, AuthenticationException $exception)
    {
        if ($request->expectsJson()) {
            return response()->json(['error' => 'Unauthenticated.'], 401);
        }

		// this is where you change the route
        return redirect()->guest(route('admin.login'));
    }

```


[go back home][home]


### how to create multiple authentication

1. create auth

```
php artisan make:auth
```

2. create admin model and migration table

```
php artisan make:model Admin -m
```

3. copy user migration from `nameOfApp/database/migrations` and paste it into admin
migration

```php
// inside admins migration schema

public function up()
{
    Schema::create('admins', function (Blueprint $table) {
        $table->increments('id');
        $table->string('name');
        $table->string('email')->unique();
        $table->string('password');
        $table->rememberToken();
        $table->timestamps();
    });
```
4. Migrate the tables

```
php artisan migrate
```

5. also copy the user model to the admin model

```php
<?php

namespace App;

use Illuminate\Notifications\Notifiable;
use Illuminate\Foundation\Auth\User as Authenticatable;

class Admin extends Authenticatable
{
    //
    use Notifiable;

    protected $guard = "admins";

    protected $fillable = ['name','password'];

    protected $hidden = ['password','remember_token'];
}
```

6. add admin guard to  `config/auth.php`

```php
'guards' => [
       'web' => [
           'driver' => 'session',
           'provider' => 'users',
       ],

       'api' => [
           'driver' => 'token',
           'provider' => 'users',
       ],

       'admin' => [
           'driver' => 'session',
           'provider' => 'admins',
       ],
       'admin-api' => [
           'driver' => 'token',
           'provider' => 'admins',
       ],

   ],

   'providers' => [
       'users' => [
           'driver' => 'eloquent',
           'model' => App\\User::class,
       ],

       'admins' => [
           'driver' => 'eloquent',
           'model' => App\Admin::class,
       ],

   ],
```

7. create a Admin controller

```
php artisan make:controller AdminController
```

8. create a AdminLogin controller

```
php artisan make:controller  AdminLoginController
```

9. copy all this shit into Admin controller

```php
/**
 * Create a new controller instance.
 *
 * @return void
 */
public function __construct()
{
    $this->middleware('auth:admin');
}

/**
 * Show the application dashboard.
 *
 * @return \Illuminate\Http\Response
 */
public function index()
{
    return view('admin');
}
```

10. duplicate login blade template from `/resources/views/auth/` and change the name to
admin-login. Make minor modifications into the template by making sure the name
**Admin** is placed in the blade file. Also **make sure you change the route name in the form to**
`admin.login.submit`

```
// At line 8
    <div class="panel-heading">ADMIN Login</div>
```
```
// At line 11
    <form class="form-horizontal" method="POST" action="{{ route('admin.login.submit') }}">
```

11. duplicate the home blade and name it admin. Add the name admin into the file
so that you know you logged in as admin

```
<div class="panel panel-default">
    <div class="panel-heading">ADMIN Dashboard</div>
```

12. add this into `/routes/web.php`

```php
Route::prefix('admin')->group(function() {
  Route::get('/login', 'AdminLoginController@showLoginForm')->name('admin.login');
  Route::post('/login', 'AdminLoginController@login')->name('admin.login.submit');
  Route::get('/', 'AdminController@index')->name('admin.dashboard');
  Route::get('/logout', 'AdminLoginController@logout')->name('admin.logout');

  // Password reset routes
  Route::post('/password/email', 'AdminForgotPasswordController@sendResetLinkEmail')->name('admin.password.email');
  Route::get('/password/reset', 'AdminForgotPasswordController@showLinkRequestForm')->name('admin.password.request');
  Route::post('/password/reset', 'AdminResetPasswordController@reset');
  Route::get('/password/reset/{token}', 'AdminResetPasswordController@showResetForm')->name('admin.password.reset');
});
```
13.  Add this into AdminLoginController

```php
public function __construct()
{
  $this->middleware('guest:admin');
}

public function showLoginForm()
{
  return view('auth.admin-login');
}

public function login(Request $request)
{
  // Validate the form data
  $this->validate($request, [
    'email'   => 'required|email',
    'password' => 'required|min:6'
  ]);

  // Attempt to log the user in
  if (Auth::guard('admin')->attempt(['email' => $request->email, 'password' => $request->password], $request->remember)) {
    // if successful, then redirect to their intended location
    return redirect()->intended(route('admin.dashboard'));
  }

  // if unsuccessful, then redirect back to the login with the form data
  return redirect()->back()->withInput($request->only('email', 'remember'));
}
```

14. create AdminResetPasswordController and add this

```php
/*
|--------------------------------------------------------------------------
| Password Reset Controller
|--------------------------------------------------------------------------
|
| This controller is responsible for handling password reset requests
| and uses a simple trait to include this behavior. You're free to
| explore this trait and override any methods you wish to tweak.
|
*/

use ResetsPasswords;

/**
 * Where to redirect users after resetting their password.
 *
 * @var string
 */
protected $redirectTo = '/admin';

/**
 * Create a new controller instance.
 *
 * @return void
 */
public function __construct()
{
    $this->middleware('guest:admin');
}

protected function guard()
{
  return Auth::guard('admin');
}

protected function broker()
{
  return Password::broker('admins');
}

public function showResetForm(Request $request, $token = null)
{
    return view('auth.passwords.reset-admin')->with(
        ['token' => $token, 'email' => $request->email]
    );
}
```

15. create AdminForgotPasswordController and add this

```php
/*
|--------------------------------------------------------------------------
| Password Reset Controller
|--------------------------------------------------------------------------
|
| This controller is responsible for handling password reset emails and
| includes a trait which assists in sending these notifications from
| your application to your users. Feel free to explore this trait.
|
*/

use SendsPasswordResetEmails;

/**
 * Create a new controller instance.
 *
 * @return void
 */
public function __construct()
{
    $this->middleware('guest:admin');
}

protected function broker()
{
  return Password::broker('admins');
}

public function showLinkRequestForm()
{
    return view('auth.passwords.email-admin');
}
```

16. in `/app/Exceptions/Handler.php` add this to the **report method**

```php
if($exception instanceof AuthenticationException){
           $guard = array_get($exception->guards(),0);

           switch($guard){
               case 'admin':
                   $login = 'admin.login';
                   break;

               default:
                   $login = 'login';
                   break;
           }
           return redirect()->guest(route($login));

       };
       parent::report($exception);
```

17. in `/app/Http/Middleware/RedirectIfAuthenticated.php` add this to the handle method

```php
public function handle (){

    switch ($guard) {
      case 'admin':
        if (Auth::guard($guard)->check()) {
          return redirect()->route('admin.dashboard');
        }
        break;

      default:
       if (Auth::guard($guard)->check()) {
            return redirect('/home');
        }
        break;
    }

    return $next($request);

}


```

[go back home][home]

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
