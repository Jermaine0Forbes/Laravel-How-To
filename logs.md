# laravel logs

## 10/17/17

### how to format date data

```
    {{$post->updated_at->format('m/d/y')}}

    // this will output the date in a day / month / year format
    // for example: 10/17/17
```

### how to format a date in a human readable format

```
    {{$post->updated_at->diffForHumans()}}

    // for example: 0 seconds ago
```

### method field function
in laravel the method field function replaces the **post** request for patch,
delete, and put since most browsers only operate on post and get

```
<form  >

{{ method_field('PATCH')}}
 ...
```

### to check the route name
Route::is checks the route name for  the current route that you are in and returns
the bool value. This is greate if you want to make things visible on some routes or
not.

````
@if( Route::is('post.index'))
     do something
@else
    do something else
@endif

```


## 10/13/17

### getting recent data

This will get the data in ascending order

```
public function index($id){

    $post = Post::latest()->get();

    return view('post',['blog' =>$post]);
}
```

### this command creates a model and a migration

```
php artisan make:model <insert name> -m
```

### what does this tinker do?

**reference**
- [laravel-news](https://laravel-news.com/laravel-tinker)

So I keep seeing tinker in a tutorial about laravel. And I believe it can show you
data inserted from the database, the code of functions, the code of classes and other things

```
    php artisan tinker

    App\Post::all();

    // this will get all the data from the Post model and print it to the terminal
```

### creating custom methods in model?

So I am watching a tutorial on how to do comments in laravel. And they just made a
addComment method in a model that they were using in a controller method. I want
to copy what I saw but I don't know how useful it will be to me

```

public function addComment(){

}
```

## 10/12/17

### One of the ways to do a form validation

```php
<?php

public function store(Request $req){

    $this->validate(request(),[
        'title' => 'required|min:12',
        'body' => 'required'
    ])
}


```
#### I think this is the second way

```php
<?php

public function store(Request $request){

            $request->validate([
            'title' => 'required|unique:posts|max:255',
            'body' => 'required',
            'publish_at' => 'nullable|date',
        ]);
}


```

### if you want to print out form validation errors on the view page

make sure you put this somewhere in the form page so that it will return the validation
errors. I am assuming the **$errors**  variable is global so you can call it anytime

```php
@if($errors->any())
  <div class="alert alert-danger">
    <ul>
    @foreach ($errors->all() as $err )
        <li > {{$err}}</li>
    @endforeach
    </ul>
  </div>

@endif

```

## 8/30/17

### tasks
- I am just going to take notes and see how far I get. I am trying to do this
**auth** shit.

### first step is to create auth or something
1. okay so I typed in the terminal `php artisan make:auth`, and it told me that
the authentication scaffolding has been made succesfully.
- so the **make auth** command does several things. First it creates several
folders in the views folder called **auth and layout**. Then it creates a **home**
view and adds in routing to the **web.php**

### how to redirect after login, register, or resetting password
Simple, in the **LoginController, RegisterController, and ResetPasswordController**
add the property `protected redirectTo = "\"`  to whatever you want

### you can customize the login controller?
Apparently you can change the login field it checks by creating a username method
in the controller to replace the **email** field. They show me an example on the website
, but I'm not sure if I did everything I needed to do to make sure that it will check a username
```
public function username()
{
return 'username';
}
```
### what the hell is guard?
So I'm reading the information, and it is telling me that the `Auth::guard()` is
used to authenticate and register users and I can **customize** it in the auth controllers?
Wait, what the fuck am I actually customizing? Also why is it useful?

Alright so I have done some reading on guarding and it essentially is the component that
checks whether you are an authenticated user or not, and is responsible for redirecting you
. Here are some articles that talk about it  
1. [Multiple authentication guard drivers](https://mattstauffer.co/blog/multiple-authentication-guard-drivers-including-api-in-laravel-5-2/) :
Their definition: **The default authentication guard in Laravel prior to 5.2 (now named the web guard) is your traditional web-based application authentication layer: username and password post to a controller, which checks the credentials and redirects if they are invalid; if valid, the user information gets saved to the session.**
2. [Stackoverflow](They're the definition of how the system should store and retrieve information about your users.) :
Someones definition: **They're the definition of how the system should store and retrieve information about your users.**

I have been reading a number of articles about guards, their purpose, and other things like
the drivers and providers of guards. So I sort of have an understanding of what is going on a little bit
. So the guard checks to see if the information that you enter is a valid username and password.  With the **provider**
property it  will check mysql table that the provider is assigned to (by default it is assigned users). And
the **drivers** property creates some type of code that allows the server to determine if you are still signed
in or not. So far I am aware of **session** and **token**. So a session is a cookie that stores information about
the user for a small frame of time so that the user will stay logged on. However, sessions do not work on mobile
applications that well so a lot of people use **tokens** to store information about the user. I know it is even more
complicated than that, but that I what I got so far. Also when you customize a guard like the example below

```php
use Illuminate\Support\Facades\Auth;

protected function guard()
{
return Auth::guard('guard-name');
}
```
essentially, you are calling a guard that you have created in the auth file that is
located in `config\auth.php`. There you can add in new auths and customize the auth properly


### so about migrations
if you try to register a user without doing migrations of the user table and the password_resets
you will get an error from laravel. So in order to avoid all just type `php artisan migrate`


### another thing to note about the auth middleware

```php
Route::get('/got', ['middleware'=>['auth'], 'uses' => function(){
    echo "I got you by the pussy hole";
}]);
```
Adding this to you routes will check if you are logged in or not. If you are not then
it will redirect you back to the login page to login because the **auth** middleware
is being used. But, if I was logged in I would receive the message **"I got you by the pussy hole"**

## 8/28/17

### tasks
- I am trying to learn how to do use laravel auth one step at a time
