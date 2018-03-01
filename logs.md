# laravel logs

## 2/29/18

Okay, so I am finding out that dusk cannot run on a server and that you possibly need 
to use phantom.js to make it work. I will investigate that later


## 2/28/18

### use DatabaseTransactions if you are going to use PHP Testing

I need to remember to inlcude the DatabaseTransactions class in whatever test example 
when testing out the database or an eloquent model

`use Illuminate\Foundation\Testing\DatabaseTransactions`


### Error: Cannot open file "/home/jermaine/lavy/bootstrap/autoload

I got this error when trying to use dusk. I see something on [github](Cannot open file "/home/jermaine/lavy/bootstrap/autoload) that I am going to
try, wish me luck

### Error: Failed to connect to localhost port 9515: Connection refused

I'm still trying to learn how to use this php unit testing and I realize
that all the tutorials that I have been looking at are antiquated because the 
methods to use them don't exist anymore. This is why I am trying to use dusk but Im 
getting errors messages as well. I think this error message is for the fact that I am
using localhost to see my laravel app. But, I am not too sure

### Doing too much shit just for dusk

I am getting the connection refused error, but I am trying some technique that is said to work 
for dusk  

---
## 1/5/18

### Note about CKEditor 

It sucks, well, at least the free version sucks. I was trying to get the 
editor to not strip away the classes in the elements for about ... a long time
I was looking through the documentation, trying to figure out how to configure  
this editor. However, I still have not succeeded in this simple task so I am moving 
on to other wysiwyg editors


---
## 1/4/18

### TokenMisMatchException in Laravel 5.4

If you get this error it could be either two things

1. You don't have the csrf_token in the form 

```php

 {{ csrf_field() }}
```

2. You have more than one submit buttons

---
## 10/25/17

### cache:clear?

**reference**
- [stackoverflow](https://stackoverflow.com/questions/43718391/laravel-throws-the-bootstrap-cache-directory-must-be-present-and-writable-erro)

I think the purpose of `php artisan cache:clear` is to refresh the application . I found out that when you
change `app:name` and you try to go to the website you get an error, unless you do **cache:clear**.  So if I ever
change anything in the `config\app.php` location I need to run cache:clear in order for it to save or refresh the
changes that I made.



---
## 10/24/17

### different ways to update data

**reference**
- [laracasts](https://laracasts.com/discuss/channels/general-discussion/update-multiple-records-using-eloquent)
- [Stackoverflow](https://stackoverflow.com/questions/32473870/how-to-update-a-record-in-laravel-eloquent)

I have seen two ways so far to update data. This is one I am going to show will
be good if you are trying to update multiple rows of data

```
public function store(){

    User::where('name','john')->update('sex','female');
}

```
#### OR


```
public function store(){

    $user = User::find(10);
    $user->name  = "myBooty";
    $user->save();
}

```


---
## 10/19/17

### the location to find Auth::routes()
`/vendor/laravel/framework/src/Illuminate/Routing/Router.php`

Use the find method and search for **auth**. There you will find all of the routes

### Some information about Facades, things that look like this Class::method()
[sitepoint](https://www.sitepoint.com/how-laravel-facades-work-and-how-to-use-them-elsewhere/)

### helpers and facades

**Auth::guard()** this is a facade

**auth()->guard()** this is a helper function

apparently they both do the same thing and there is not really a difference in
when to use these methods, so you can use one or the other

### static methods?

` static::selectRaw( select * from Post)`, If you see something like this where the
static keyword is in front of the command, then I believe it is return a value from
a facade. You know the class that call methods like `Post::comments()`. Here is an example

```
// In controller

public function show(){

    $post = Post::archives();
}

```
```
// In model

public static function archives(){

    return static::selectRaw(select month, year from archives )
    ->groupBy('month');
}

```

### view composer

`view->composer()` : Allows you to add a variable to any view template that you
want . Make sure you go to `./app/Providers/AppServiceProvider.php`, and add the
 code in the **boot** method in order for it to work. This is what I saw in the tutorial

```
public function boot(){

    $post = new Post;

    view()->composer('layouts.sidebar', function($view){
            $view->with('sidebar', $post->archives() )
        })
}
```

### view()->with()

The _with_ method is similar to doing `return view('home',['var'=>$data])`, except
you do `return view('home')->with('var',$data)` instead.

### dependency injection, what does it mean?

[sitepoint](https://www.sitepoint.com/dependency-injection-laravels-ioc/)

I have no fucking clue. All the examples I see of it have to do with you passing a
class into a method or constructor of another class. So I am assuming that is what it
means. I think I read an article that said it is passing a component into a method of
a class, but the component is a class though so... yeah.

### App::bind does ...

I don't know, all I am hearing throughout this tutorial is about service containers.
I don't know useful service containers are and why should I give a fuck. I might have
to look into what a **service container**  purpose is anyways.

---
## 10/18/17

### finally learned how to use form builder from laravel
First off, you need to go to [this](https://laravelcollective.com/docs/5.4/html) website to learn how to download and add
the classes in the config/app file in order for it to run. Then you need to look
at the [api](https://laravel.com/api/5.4/Illuminate/Html/FormBuilder.html).This
information will show you how to parameters to the most common methods that you
will use to create form elements like **submit, text,textarea, input,label** and the
like. I still don't know why it would be advantageous to use this method instead of
just creating forms with regular html and adding a csrf_token

### things to remember

this is a simple way to login

```
    public function store(){

        $this->validate([
            'name' => 'required',
            'password' => 'required',
            'email' => 'required|email'
            ]);

        $user = User::create(request([
             'name',
             'email',
             'password'
            ]));

        auth()->login($user);
    }

```

this is a simple way to logout

`auth()->logout();`

### password confirmation

In order to have a password confirmation in laravel you need to add **confirm** in
the validate method and have a **_confirmation** as the name to a field

```
// In form

<div class="form-group">
    <label for="password_confirmation">Password Confirmation </label>
    <input type="password" name="password_confirmation" />
</div>

```


```
// In controller
public function store(){

    $this->validate([
        'name' => 'required',
        'password' => 'required|confirm',
        'email' => 'required|email'
        ]);

        ....
}
```

### Auth::check()

okay, based on the tutorial I am watching I believe that this method is to check
whether a user is signed in or not. The method seems to return a boolean value and
if it is true then you will execute some code

```
@if(Auth::check())
    //do something
@endif

```

### auth()->attempt()

I think this checks if your login credentials are valid or not.

```
// In controller

if(!auth()->attempt(request(['username','password']))){

    return back();
}

```
---
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

```
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
