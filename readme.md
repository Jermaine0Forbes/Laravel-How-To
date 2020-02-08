# Laravel How To

## Installation
- [how to setup laravel][laravel]
- [how to create a project with composer][create-project]
- [how to remove 500 internal server error][500]
- [how to generate a new application key][new-key]
- [how to make your laravel project work when pulling it from github][pulling]
- [how to install Voyager][install-voyager]
- [how to check the verion of laravel][version]

## Carbon
- [Carbon table][carbon]
- [how to include carbon][inc-carbon]

## Controller
- [how to create a controller][control]
- [how to create a single action controller][single-control]
- [how to create a controller with all the CRUD methods][crud-control]

## Errors
- [The bootstrap/cache directory must be present and writable][boot-error]
- [The only supported ciphers are AES-128-CBC and AES-256-CBC with the correct key lengths][cipher-error]
- [The stream or file "path/to/file" could not be opened: failed to open stream: Permission denied][per-err]
- [Declaration of App\Providers\EventServiceProvider::boot(Illuminate\Contracts\Events\Dispatcher $events) should be compatible with Illuminate\Foundation\Support\Providers\EventServiceProvider::boot()][event-boot]
- [Route {route} not defined.][route-undef]

## Events
- [how to create an event][create-event]
- [what is the purpose of creating events]

## File Storage
- [how to create a public disk][public-disk]
- [how to publicly store a file][file-store-public]
- [how to retrieve a file][file-retrieve]

## Form
- [how to create a proper form structure][form]
- [form builder table][form-table]
- [how to retrieve the previous values from a form][old-field]
- [how to validate form fields][val-form]
- [how to output failed validation fields]
- [validating rule options]


## Mail
- [how to send mail to your gmail for the first time][first-mail]
- [how to send mail the simple way][mail-simple]
- [how to send mail with Mailable][mailable]
- [how to make a markdown Mailable][md-mailable]
- [how to send a markdown Mailable][md-send]
- [how to customize markdown components][customize-components]
- [how to customize markdown css][md-css]
- [how to preview markdown Mailable][preview-mailable]
- [how to pass data to a Mailable][data-mailable]


## Model
- [how to create a model][create-model]
- [how to alter the model name][name-model]
- [how to change primary key name][prime-name]
- [how to disable timestamps][timestamps]
- [how to add your database information][data-info]
- [how to change the created and updated timestamps][create-update]
- [how to create a model and migration][model-migrate]
- [how to create a hasMany relationship][hasMany]
- [how to create a belongsTo relationship][belongsTo]
- [how to use Carbon methods on datetime data][carbon-meth]
- [how to create a model, migration, and controller at the same time][create-alot]


## Middleware
- [how to create a middleware][middleware]
- [make middleware global][global-middleware]
- [how to do a basic middlware][basic-middleware]

## Mix/Webpack
- [how to make 'npm run dev' work][mix-work]
- [how to make typescript work][typescript]


## Other
- [how to add wysiwyg editor in laravel][wysiwyg]
- [how to create a search engine][search-engine]
- [how to create a 404 page][404-page]

## ORM
- [how to create data][create-data]
- [how to update data][update-data]
- [how to delete data][delete-data]

## PHP Unit

- [how to test databases with phpunit][data-phpunit]
- [how to setup a basic phpunit test][basic-phpunit]

## Queue

- [how to make a simple queue][simple-queue]

## Seeding / Faker
- [how to generate a factory for fake data][fake-data]
- [how to create the fake data][create-fake]
- [faker reference table][faker-reference]


## View
- [how to extend a blade layout][extend]
- [how to include files ][include]
- [how to unescape html][html-unescape]
- [how to use @auth][@auth]
- [how to create components][create-component]
- [how to add parameters to a route component][route-parameter]
- [how to use @foreach][@foreach]
- [view template table][template-table]


[old-field]:#how-to-keep-old-values-from-a-form-field
[simple-queue]:#how-to-make-a-simple-queue
[route-undef]:#route-not-defined-error
[create-event]:#how-to-create-an-event
[create-data]:#how-to-create-data
[update-data]:#how-to-update-data
[delete-data]:#how-to-delete-data
[version]:#how-to-check-your-version-of-laravel
[basic-middleware]:#how-to-do-a-basic-middleware
[event-boot]:#eventserviceprovider-boot-error
[inc-carbon]:#how-to-include-carbon
[template-table]:#view-template-table
[per-err]:#the-stream-or-file-could-not-be-opened
[route-parameter]:#how-to-add-parameters-to-a-route-component
[public-disk]:#how-to-create-a-public-disk
[create-component]:#how-to-create-components
[customize-components]:#how-to-customize-markdown-components
[data-mailable]:#how-to-pass-data-to-a-mailable
[cipher-error]:#the-only-supported-ciphers-are
[boot-error]:#the-bootstrapcache-directory-must-be-present-and-writable
[install-voyager]:#how-to-install-voyager
[data-phpunit]:#how-to-test-databases-with-phpunit
[basic-phpunit]:#how-to-setup-a-basic-phpunit-test
[faker-reference]:#faker-reference-table
[create-fake]:#how-to-create-fake-data
[fake-data]:#how-to-generate-fake-data
[carbon]:#carbon-table
[@auth]:#how-to-use-auth
[md-css]:#how-to-customize-markdown-css
[preview-mailable]:#how-to-preview-a-markdown-mailable
[404-page]:#how-to-create-a-404-page
[create-alot]:#how-to-create-a-model-migration-and-controller
[md-send]:#how-to-send-a-markdown-mailable
[md-mailable]:#how-to-make-a-markdown-mailable-in-the-terminal
[mailable]:#how-to-send-mail-with-mailable
[mail-simple]:#how-to-send-mail-the-simple-way
[first-mail]:#how-to-send-mail-to-your-gmail-for-the-first-time
[carbon-meth]:#how-to-use-carbon-on-datetime-data
[html-unescape]:#how-to-unescape-html
[global-middleware]:#make-middleware-global
[middleware]:#how-to-create-a-middleware
[file-retrieve]:#how-to-retrieve-a-file
[file-store-public]:#how-to-publicly-store-a-file
[typescript]:#how-to-make-typescript-work
[mix-work]:#how-to-make-npm-run-dev-work
[search-engine]:#how-to-create-a-search-engine
[wysiwyg]:#how-to-add-wysiwyg-editor-in-laravel
[include]:#how-to-include-files
[belongsTo]:#how-to-create-a-belongsto-relationship
[hasMany]:#how-to-create-a-hasmany-relationship
[model-migrate]:#how-to-create-a-model-and-migration
[form-table]:#form-builder-table
[form]:#how-to-create-a-proper-form-structure
[crud-control]:#how-to-create-a-controller-with-all-the-crud-methods
[laravel]:#how-to-setup-laravel
[pulling]:#how-to-make-your-laravel-project-work-when-pulling-it-from-github
[home]:#laravel-how-to
[extend]:#how-to-extend-a-blade-layout
[control]:#how-to-create-a-controller
[data-info]:#how-to-add-your-database-information
[create-project]:#how-to-create-a-project-with-composer
[new-key]:#how-to-generate-a-new-application-key
[500]:#how-to-remove-500-internal-server-error
[create-model]:#how-to-create-a-model
[name-model]:#how-to-alter-model-name
[prime-name]:#how-to-change-primary-key-name
[timestamps]:#how-to-disable-timestamps
[create-update]:#how-to-change-the-timestamps
[single-control]:#how-to-create-a-single-action-controller
[@foreach]:#how-to-use-foreach

---


### how to keep old values from a form field

<details>
<summary>
View Content
</summary>

:link: **Reference**
- [old helper](https://laravel.com/docs/5.7/helpers#method-old)
---

The `old` helper function allows you to retreive the old values from the previous
request. If you submit a form and there is possibly a validation error. When you
redirect to the original form you should have the old values in the fields

:exclamation: **Note:** the `old` helper will not keep the value of the password
field

---

**In the form**

```php
@section('content')
  <div class="container">
      <div class="row">
          <div class="col-md-8 justify-content-center">
             <h1>Login into your account</h1>
             <form class="" action="/form" method="post">
                 {{ csrf_field() }}
               <div class="form-group">
                 <h4><label for="">Enter your Email</label></h4>
                 <!-- using the old helper function will get the previous email value -->
                 <input type="email" name="email" value="{{old('email')}}">
               </div>
               <div class="form-group">
                 <h4><label for="">Enter your Username</label></h4>
                 <!-- using the old helper function will get the previous username value -->
                 <input type="text" name="username" value="{{old('username')}}">
               </div>
               <div class="form-group">
                  <h4> <label for="">Enter your Passowrd</label></h4>

                 <input type="password" name="password"  value="{{old('password')}}">
               </div>
               <div class="form-group">
                 <input type="submit" class="btn btn-primary" value="submit">
               </div>
             </form>

          </div>
      </div>
  </div>
@endsection
```

**Inside the controller**

```php

public function form(){ //url  GET: /form
  return view("form");
}

public function storeForm(Request $req){//url POST: /form
  $data = $req->validate([
    'email' => 'required|email:rfc|max:16',
    "username" => 'required|alpha_num|max:4',
    'password' => 'required|max:16'
  ]);// if the validation fails, laravel will redirect to the original page.


  dump("$req->email has been successfully created");
}
```

</details>

[go back :house:][home]



### how to make a simple queue

<details>
<summary>
View Content
</summary>

:link: **Reference**
- [Why Laravel Queues Are Awesome](https://scotch.io/tutorials/why-laravel-queues-are-awesome)
---

:exclamation: **Note:**

---

- create queue:table and migrate it
- in the `.env` file change **QUEUE_DRIVER** to database
- create job with the `make:job` command
- Find the job file that you created and add in the logic that you need to execute
in the *handle* method
- now in your controller import the job in the file, and execute it by calling the *dispatch* method
- finally, type in the command line `queue:listen`

```php

```

</details>

[go back :house:][home]



### how to create an event
<details>
<summary>
View Content
</summary>

:link: **Reference**
- []()
---

:exclamation: **Note:** In this example I am creating a simple event that will trigger when a  person sends
their email and donation amount through a form. I did not link up any advanced code to
receive a transaction or send an email to the person.



1. make an controller and call it DonateController

```
 php artisan make:controller DonateController
```
2. make a view called `donate.blade.php` that has a form that has an email field and donation amount field. like this

```php
@extends('layouts.app')

@section('content')
  <div class="container">
      <div class="row">
          <div class="col-md-8 justify-content-center">
             <h1>Donate for Charity</h1>
             <form class="" action="/donate" method="post">
                 {{ csrf_field() }}
               <div class="form-group">
                 <h4><label for="">Email</label></h4>

                 <input type="email" name="email" value="">
               </div>
               <div class="form-group">
                  <h4> <label for="">Amount</label></h4>

                 <input type="number" name="amount" min="0" value="">
               </div>
               <div class="form-group">
                 <input type="submit" class="btn btn-primary" value="submit">
               </div>
             </form>
          </div>
      </div>
  </div>
@endsection

```
- In `web.php` file create a get & post donate route. like this

```php
Route::get("/donate","DonateController@index");
Route::post("/donate","DonateController@store");

```

3. in the DonateController, create the methods and make the index method return the view **donate** that has the forms .

```php
class DonateController extends Controller
{
    public function index(){
      return view("donate");// shows the form

    }

    // public function store(Request $req){
    //   event(new UserDonated($req));
    // }
}
```

4. in the `store` method add in the event helper and create a new instance of **UserDonated**

```php
use App\Events\UserDonated;
class DonateController extends Controller
{
    public function index(){
      return view("donate");// shows the form

    }

    public function store(Request $req){
      event(new UserDonated($req));//This event will use request object to get the values
    }
}
```

5. now go to **EventsServiceProvider** by going to `app\Providers\EventsServiceProvider`
in the *listen* property add a new event called `UserDonated`, and then add  listeners called `EmailToDonator` and `StoreDonation`


```php

class EventServiceProvider extends ServiceProvider
{
    /**
     * The event listener mappings for the application.
     *
     * @var array
     */
    protected $listen = [
      'App\Events\UserDonated' => [
          'App\Listeners\EmailToDonator',
          'App\Listeners\StoreDonation',
      ],
    ];
}
```

6. now go into the console and type `php artisan event:generate`, this will create the events and listeners

7. go to the `UserDonated` event  and make sure you create a property that will take
the request property

```php

use Illuminate\Http\Request;

class UserDonated
{
    use Dispatchable, InteractsWithSockets, SerializesModels;

    /**
     * Create a new event instance.
     *
     * @return void
     */
    public function __construct(Request $request)
    {
        $this->request = $request;
    }


}
```


- Now in the listeners create any logic that will grab the request info and use it to
*store the donation* and *email that the donation has been received*.

**In StoreDonation.php**

```php

class StoreDonation
{
    /**
     * Create the event listener.
     *
     * @return void
     */
    public function __construct()
    {
        //
    }

    /**
     * Handle the event.
     *
     * @param  UserDonated  $event
     * @return void
     */
    public function handle(UserDonated $event)
    {
      $amount = $event->request->input("amount");
      dump("We've received your amount of $amount");
    }
}
```
**In EmailToDonator.php**

```php

class EmailToDonator
{
    /**
     * Create the event listener.
     *
     * @return void
     */
    public function __construct()
    {
        //
    }

    /**
     * Handle the event.
     *
     * @param  UserDonated  $event
     * @return void
     */
    public function handle(UserDonated $event)
    {
        $email = $event->request->input("email");
        dump("We've sent you a message to $email");
    }
}


```

- So when you make post or save a form the event should trigger the `UserDonated` event
which should also trigger the listeners



</details>
[go back :house:][home]

### route not defined error

<details>
<summary>
View Content
</summary>

:link: **Reference**
- []()

if you get this error, then you probably forgot to attach the name method
`->name('nameofroute')` to your `Route` facade

</details>

[go back :house:][home]

### how to save data

<details>
<summary>
View Content
</summary>
:link: **Reference**
- [Inserts](https://laravel.com/docs/6.x/eloquent#inserts)
---


```php
public function insert(Request $req){
  $pokemon = new poke;

  $pokemon->name = $req->name;

  $pokemon->save();

}
```

</details>

[go back :house:][home]

### how to delete data

<details>
<summary>
View Content
</summary>

:link: **Reference**
- [Deleting Models](https://laravel.com/docs/6.x/eloquent#deleting-models)
---

:exclamation: **Note:**

---

**If you want to delete one row**

```php
Question::destroy($id); // deletes a row by the id

return redirect("questions");
```

**If you want to delete multiple rows**

```php
App\Flight::destroy(1);

App\Flight::destroy(1, 2, 3);

App\Flight::destroy([1, 2, 3]);

App\Flight::destroy(collect([1, 2, 3]));
```

</details>

[go back :house:][home]




### how to update data
<details>
<summary>
View Content
</summary>

:link: **Reference**
- [Updates](https://laravel.com/docs/6.x/eloquent#updates)
---

**Update method #1**

```php
Question::where("id", $id)
->update([
	"question" => $req->input("question"),
	"section" => $req->input("section"),
	"subsection" => $req->input("subsection"),
	"answer" => $req->input("answer")
]);
```


**Update method #2**

```php
$quest = Question::find(1);

$quest->name = "how do you ask a question";

$quest->save()
```



</details>

[go back :house:][home]

### how to check your version of laravel

<details>
<summary>
View Content
</summary>

```
php artisan --version
```

</details>

[go back :house:][home]





### how to do a basic middleware

<details>
<summary>
View Content
</summary>

:link: **Reference**
- [Authentication Middleware and Redirects](https://www.youtube.com/watch?v=gHPMtA7kIPQ)
---

1. In the terminal create a middleware like this

```
php artisan make:middleware CheckSex
```

2. Next, let's create a controller that will hold the logic of any routes

```
php artisan make:controller SexController
```

3. Inside the controller make two methods like this


```php

namespace App\Http\Controllers;

use Illuminate\Http\Request;

class SexController extends Controller
{

    public function __construct(){

    }

    // This will be the initial view that will be seen if everything checks out
    public function index($sex){
      return view("male");
    }

    //this method will be called if you go the uri of /female or an sex object
    //will have female as the value
    public function female(){
      return view("female");
    }
}
```

4. Now in the views folder `resources/views` create a male & female view like this

**male.blade.php**
```
<h1> You are a male</h1>

```
**female.blade.php**
```
<h1> You are a female</h1>

```

5. Now, go to the routes in `web/routes.php` and add this

```php
//so this route will check if you put female, male, or anything else
Route::get("/sex/{sex}", "SexController@index")->middleware("checksex");

// the uri will just transport you to the female view
Route::get("/female", "SexController@female");
```

6. Your new middleware file should be located in `app/Http/Middlware/CheckSex.php`
and add your own logic to it

```php
namespace App\Http\Middleware;

use Closure;

class CheckSex
{
    /**
     * Handle an incoming request.
     *
     * @param  \Illuminate\Http\Request  $request
     * @param  \Closure  $next
     * @return mixed
     */
    public function handle($request, Closure $next)
    {   // if the request of sex equals female
        // then redirect the user to female uri
        // but if it is something else then get out of the middleware
        if($request->sex == "female"){
          return  redirect("/female");
        }

        return $next($request);
    }
}

```

7. Finally, go to `app/Http/Kernel.php` and add the CheckSex class to the **$routeMiddleware**

```php
protected $routeMiddleware = [
    'auth' => \App\Http\Middleware\Authenticate::class,
    'auth.basic' => \Illuminate\Auth\Middleware\AuthenticateWithBasicAuth::class,
    'bindings' => \Illuminate\Routing\Middleware\SubstituteBindings::class,
    'cache.headers' => \Illuminate\Http\Middleware\SetCacheHeaders::class,
    'can' => \Illuminate\Auth\Middleware\Authorize::class,
    'guest' => \App\Http\Middleware\RedirectIfAuthenticated::class,
    'signed' => \Illuminate\Routing\Middleware\ValidateSignature::class,
    'throttle' => \Illuminate\Routing\Middleware\ThrottleRequests::class,
    'verified' => \Illuminate\Auth\Middleware\EnsureEmailIsVerified::class,
    'checksex' => \App\Http\Middleware\CheckSex::class // add your middleware like this
    // you don't have to name your middleware the same thing you could change the
    // name if you wanted to
];


```

8. So basically if you go to /sex/male, the middleware will allow you to go the male
view. However, if you put in the parameter /sex/female it will redirect you to the
female view.

</details>

[go back :house:][home]

### EventServiceProvider boot error

<details>
<summary>
View Content
</summary>

**reference**
- [Laravel: Declaration of App\Providers\EventServiceProvider::boot](https://stackoverflow.com/questions/44788352/laravel-declaration-of-app-providers-eventserviceproviderboot)

**If you get this**

`Declaration of App\Providers\EventServiceProvider::boot(Illuminate\Contract
  s\Events\Dispatcher $events) should be compatible with Illuminate\Foundatio
  n\Support\Providers\EventServiceProvider::boot()
`

**or this**

` Declaration of App\Providers\RouteServiceProvider::boot(Illuminate\Routing\
  Router $router) should be compatible with Illuminate\Foundation\Support\Pro
  viders\RouteServiceProvider::boot()`

Then comment out the boot function in `RouteServiceProvider` and `EventServiceProvider`
like this

```php
// public function boot(Router $router)
// {
//     //
//
//     parent::boot($router);
// }
```
</details>

[go back :house:][home]


### view template table

<details>
<summary>
View Content
</summary>

Expression | Description
-|-
{{$var}}|Echo content
{{ $var or 'default' }}|Echo content with a default value
@extends('layout')|Extends a template with a layout
@if(condition) ...insert code @endif|Starts an if block
@section('name') ...insert code @stop|Starts a section
@while(condition) ...insert code @endwhile|Starts a while block
@include(file, ['var' => $val,...])|Includes a template, passing new variables.
@yield('section')|Yields content of a section.
</details>

[go back :house:][home]


### how to use @foreach

<details>
<summary>
View Content
</summary>

```php
@foreach( $sodas as $soda)
  <p>$soda->name</p>
  <p>$soda->company</p>
  <p>$soda->price</p>
@endforeach
```
</details>

[go back :house:][home]

### The stream or file could not be opened

<details>
<summary>
View Content
</summary>

Just do this in your terminal

```
cd your-project

sudo chmod -R 755 ./; sudo chmod -R o+w ./storage

```
</details>

[go back :house:][home]

### how to include carbon

<details>
<summary>
View Content
</summary>

```php
use Carbon\Carbon;
```

</details>

[go back :house:][home]



### How to add parameters to a route component
<details>
<summary>
View Content
</summary>

**web.php**
```php
Route::get('/home/settings/{id}', 'HomeController@settings')->name('home.setting');
```

**user-sidebar.blade.php**
```php
...
<li><a href="{{route('home.setting',[Auth::user()->id])}}">settings</a></li>
...
```
</details>

[go back :house:][home]

### How to create a public disk
<details>
<summary>
View Content
</summary>

```
php artisan storage:link
```
</details>

[go back :house:][home]


### How to create components

<details>
<summary>
View Content
</summary>

**references**
- [how do you create markdown mailable components](https://laracasts.com/discuss/channels/general-discussion/how-do-you-create-markdown-mailable-components)


1. in the `resources/views` create a folder to hold components

```
mkdir components
```

2. Now create a  blade file and add content similar to this

```
touch components/alert.blade.php
```

```php

<div style="background: yellow;">
    {{ $slot }}
</div>

```

3. Now when you try to add the component you call it like this

```php
@component('components.alert')
    This will go into the slot!
@endcomponent

```


</details>

[go back :house:][home]

### How to customize markdown components

<details>
<summary>
View Content
</summary>

This will create a vendor folder in views where you can alter components

```
php artisan vendor:publish --tag=laravel-mail
```
</details>

[go back :house:][home]


### How to pass data to a Mailable

<details>
<summmary>
View Content
</summmary>


1. create a controller, and a markdown mailable

```
php artisan make:controller <insert name>

php artisan make:mail <insert name> --markdown=<insert name>

```

2. Inside controller do this

```php
//<?php

namespace App\Http\Controllers;

use Illuminate\Http\Request;
use Illuminate\Support\Facades\Mail;
use App\Mail\mailShit; // mailShit is the name of the mail Class that I created

class MailController extends Controller
{
    //

    public function preview(){

        $data = [
            "subject" => "this is a subject",
            "email" => "jermaine@boogietown",
            "body" => "this is a body"
        ];

         return new mailShit($data); // this will preview the mail that you are sending

    }
}

```

3. In `app/Mail/<insert name>` add this to the build method

```php
//<?php

namespace App\Mail;

use Illuminate\Bus\Queueable;
use Illuminate\Mail\Mailable;
use Illuminate\Queue\SerializesModels;
use Illuminate\Contracts\Queue\ShouldQueue;

class mailShit extends Mailable
{
    use Queueable, SerializesModels;

    /**
     * Create a new message instance.
     *
     * @return void
     */

    public $mail;

    public function __construct($data)
    {
        $this->mail = $data;
    }

    /**
     * Build the message.
     *
     * @return $this
     */
    public function build()
    {	// this with method will add values from $this->mail
      // also mail.shit is located in views/mail/shit.blade.php
        return $this->markdown('mail.shit')->with($this->mail);
    }
}

```

4. In `resources/views/mail/shit.blade.php`, which is the markdown that I created

```php
@component('mail::message')
# Introduction


<!--This will output : this is a body-->
## {{$body}}

@component('mail::button', ['url' => ''])
Button Text
@endcomponent

Thanks,<br>
{{ config('app.name') }}
@endcomponent


```


</details>

[go back :house:][home]




### The bootstrap/cache directory must be present and writable

<details>
<summmary>
View Content
</summmary>

**reference**
- [stackoverflow](https://stackoverflow.com/questions/43718391/laravel-throws-the-bootstrap-cache-directory-must-be-present-and-writable-erro)

</details>

[go back :house:][home]



### The only supported ciphers are

<details>
<summmary>
View Content
</summmary>

**reference**
- [stackoverflow](https://stackoverflow.com/questions/39693312/the-only-supported-ciphers-are-aes-128-cbc-and-aes-256-cbc-with-the-correct-key)

</details>

[go back :house:][home]



### how to install voyager

<details>
<summary>
View Content
</summary>

1. create a laravel project

```
composer create-project laravel/laravel <insert name of project>
```

2. create a config file that will serve your laravel app

```
cd /etc/apache2/sites-available

sudo nano voyager.conf

// paste this into the conf file

<VirtualHost *:80>
        ServerName work.com
        DocumentRoot /var/www/html/your-project/public

        <Directory /var/www/html/your-project/public>
            AllowOverride All
            Require all granted
        </Directory>
</VirtualHost>

```

3. enable the site and reload it

```
sudo a2ensite voyager.conf

sudo service apache2 reload
```

4. allow laravel to access certain folders

```
cd <insert name of project>

sudo chmod -R 755 ./; sudo chmod -R o+w ./storage
```

5. now require voyager

```
composer require tcg/voyager
```

6. in the env file make sure you add your info

```
APP_URL=http://localhost
DB_HOST=localhost
DB_DATABASE=Voyager
DB_USERNAME=jermaine
DB_PASSWORD=secret

```

7. now install voyager

```
php artisan voyager:install
```

8. create an admin user to access the backend

```
php artisan voyager:admin your@email.com --create
```

9. now  visit your websites `http://yourWebsite.com/admin` to access the admin page


</details>

[go back :house:][home]


### how to test databases with phpunit

<details>
<summary>
View Content
</summary>

1. assuming that you already have created a model and table in the database named `Article`
you can easily follow along, if you haven't then create your own shit

2. make a test

```
php artisan make:test DataTest
```

3. in the `tests/Feature/DataTest.php` add in the DatabaseTransactions like so

```

<?php

namespace Tests\Unit;

use Tests\TestCase;
use Illuminate\Foundation\Testing\DatabaseMigrations;
use Illuminate\Foundation\Testing\DatabaseTransactions;

class DataTest extends TestCase
{

	use DatabaseTransactions;// this will prevent fake data being saved in your database
	/**
     * A basic test example.
     *
     * @return void
     */
    public function testBasicTest()
    {
        $this->assertTrue(true);
    }
}
```

4. Now create fake data with the factory like so, and add the `Article` model or
whatever model you created so that you can create fake data

```

<?php

namespace Tests\Unit;

use Tests\TestCase;
use Illuminate\Foundation\Testing\DatabaseMigrations;
use Illuminate\Foundation\Testing\DatabaseTransactions;
use App\Article; //adding the model

class DataTest extends TestCase
{

	use DatabaseTransactions;
	/**
     * A basic test example.
     *
     * @return void
     */
    public function testBasicTest()
    {

		$content = "And my balls were really chilly on that fateful day";
		// this creates a row of data
       factory(Article::class)->create([
            "title" => "It was a dark and stormy night",
            "content" => $content,
            "author_id" =>28
        ]);

		// assertContains will look at an array or string to see if second parameter
		// contains the first parameter
		$this->assertContains($content,Article::where("author_id",28)->get());



    }
}

```

5. so now run phpunit, and it should be successful because author_id=28 does contain the specific content
string

```
./vendor/bin/phpunit
```


</details>

[go back :house:][home]

### how to setup a basic phpunit test

<details>
<summary>
View Content
</summary>
1. make a test

```
php artisan make:test HomeTest
```

2. in `tests/Feature` location you will find your new test so open it up
and you will see something like this

```
<?php

namespace Tests\Feature;

use Tests\TestCase;
use Illuminate\Foundation\Testing\RefreshDatabase;

class HomeTest extends TestCase
{
    /**
     * A basic test example.
     *
     * @return void
     */
    public function testExample()
    {


    }
}

```

3. let's just create a simple test to determine if **phpunit** can access a certain page
in your website, so copy this down


```

<?php

namespace Tests\Feature;

use Tests\TestCase;
use Illuminate\Foundation\Testing\RefreshDatabase;

class HomeTest extends TestCase
{
    /**
     * A basic test example.
     *
     * @return void
     */
    public function testExample()
    {

        $response = $this->get("/");

        $response->Status(200);// this should determine if a route can be accessed

    }
}
```

4. now run the **phpunit** command

```
./vendor/bin/phpunit
```

5. Now phpunit should pass with flying colors. If it doesn't then you are doing something wrong

</details>


[go back :house:][home]

### Faker reference table

**reference**
- [faker reference](https://github.com/fzaninotto/Faker#fakerproviderlorem)

`$faker->methodName() // returns something`

method | description|example
-|-|-
randomDigit|creates a random number|7
randomElement($array = array ('a','b','c'))|gets a random value from an array you created|'b'
sentence|creates one sentence|Sit vitae voluptas sint non voluptates.
paragraph|creates one paragraph|Hella art party master cleanse, poutine twee migas...
firstName($gender = null 'male' or 'female')|self explanatory| Johnathan
lastName|self explanatory|Johnson
randomNumber($nbDigits = NULL, $strict = false)|creates a random number based on the digits you provided|234
numberBetween($min = 1000, $max = 9000)|self explanatory|8967
phoneNumber|self explanatory|201-886-0269 x3767
streetAddress|self explanatory|439 Karley Loaf Suite 897
state|self explanatory| Ohio
city|self explanatory| Tallahassee
email|self explanatory|tkshlerin@collins.com
userName|self explanatory|wade55
password|self explanatory|k&|X+a45*2[
slug|self explanatory|aut-repellat-commodi-vel-itaque

[go back home][home]

### How to create fake data

In the console write this, also make sure you generate all
the faker data before you do the command

```
php artisan db:seed
```

[go back home][home]

### How to generate fake data

1. create a factory model, also make sure that you have the database
and model created

```
php artisan make:factory Article
```

2. If you have not created a model or the table then type the command in


```

php artisan make:model  Article -m  // this creates the model and the migration table

```


3. In `databases/migrations` find the migrations table and edit it to your liking

```
<?php

use Illuminate\Support\Facades\Schema;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Database\Migrations\Migration;

class CreateSodasTable extends Migration
{
    /**
     * Run the migrations.
     *
     * @return void
     */
    public function up()
    {
        Schema::create('articles', function (Blueprint $table) {
            $table->increments('id');
            $table->string("title", "50");
            $table->text("content");
            $table->integer("author_id");
            $table->timestamps();
        });
    }

    /**
     * Reverse the migrations.
     *
     * @return void
     */
    public function down()
    {
        Schema::dropIfExists('articles');
    }
}


```

4. Migrate the table

```
 php artisan migrate
```

5. then go to `databases\factories\Article.php`, and add the faker property

```
<?php

use Faker\Generator as Faker;
use App\Article;

$factory->define(Article::class, function (Faker $faker) {
     return [
        'title' => $faker->title,
        'content' => $faker->paragraph,
        'author_id' => $faker->randomDigit
    ];
});
```

6. then go to `databases\seeds\DatabaseSeeder.php` and add the code to the
method

```
<?php

use Illuminate\Database\Seeder;
use App\Article;

class DatabaseSeeder extends Seeder
{
    /**
     * Run the database seeds.
     *
     * @return void
     */
    public function run()
    {
        // $this->call(UsersTableSeeder::class);
        factory(Article::class,1000)->create();
    }
}

```

7. finally, seed the data

```
php artisan db:seed

```

8. And that will create the rows of data

[go back :house:][home]

### Carbon Table

**reference**
- [carbon](http://carbon.nesbot.com/docs/#api-introduction)

Here are the common methods I will use with the Carbon class

method|description|example
-|-|-
now()|gets the current datetime|Carbon::now() //2018-02-23 18:11:35.0 UTC (+00:00)
addYear(year)|adds the amount of years to date, it will default to 1|Carbon::addYear(5) // 2023-02-23 18:17:38.0 UTC (+00:00)
diffForHumans()|makes the value human readable|Carbon::now()->addYear(5)->diffForHumans()  // "5 years from now"
tzName|this property gets the current timezone you are in|Carbon::now()->tzName // "UTC"
createFromDate(year,month,day,timezone)|creates a date with parameters you added|Carbon::createFromDate(2022,4,17,"America/New_York") // 2022-04-17 18:29:04.0 America/New_York (-04:00)

[go back home][home]


### HOW TO USE @auth

```php

@auth('master')

    If you are logged in under a master guard you will be able to see this

@endauth
```


[go back home][home]

### HOW TO CUSTOMIZE MARKDOWN CSS

#### How to add a new css file

1. The css that markdown uses is called `default` in
order to change it you have to go to `config/mail.php`.
And at the bottom you will see a markdown value that has
the property called **theme** change the name of the theme
to whatever the new css is called.

2. Next the location where to hold the css files should be
in `resources/views/vendor/mail/html/themes` so if you want to
see the changes take place you need add your css files in that area

#### How to add a scss file

1. You typically do the same thing that you do all the time when
you create scss files, except in the **webpack.mix.js** file you
need to create the output path like this


```js
//if you scss is name my-theme.scss then leave it alone
.sass('resources/assets/sass/mail/my-theme.scss', '../resources/views/vendor/mail/html/themes')
```

[go back home][home]

### HOW TO PREVIEW A MARKDOWN MAILABLE

1. Make sure you add the mailable you want to preview in your
contoller like this `use  App\Mail\<insert name>;`

2. In the controller add this content in your method

```php

 public function preview(){

        $data =[
            "subject" => "This is a subject",
            "email" => "skivac3@gmail.com",
            "body" => "This is a body"
        ];

    // sendMark is the markdown mailable that I created

       $mail = new sendMark($data);
       $mail = $mail->build();
       return $mail->buildView()["html"];


    }
```
3. Go to `/home/jermaine/Portfolio-Website/vendor/laravel/framework/src/Illuminate/Mail/Mailable.php`,
  find the method **buildView**, and make sure you change modifier to public

4. After that you're all good


#### 2ND OPTION

```php


public function preview(){

        $data =[
            "subject" => "This is a subject",
            "email" => "skivac3@gmail.com",
            "body" => "This is a body"
        ];

    // sendMark is the markdown mailable that I created

       return new sendMark($data);



    }

```


[go back home][home]

### HOW TO CREATE A 404 PAGE

**reference**
- [laravel](https://laravel.com/docs/5.6/errors#http-exceptions)

Create a `resources/views/errors/404.blade.php` and add your message
when a 404 error happens.

[go back home][home]

### HOW TO CREATE A MODEL, MIGRATION, AND CONTROLLER

```
php artisan make:model <insert name> -rm
```

[go back home][home]

### HOW TO SEND A MARKDOWN MAILABLE

This is pretty much 99% identical to a regular mailable
except that you need to change the `view()` to `markdown()`
for example

1. first create the markdown file. The markdown flag will create a folder called `email`
with the markdown called `mark.blade.php`

```
php artisan make:mail sendMark --markdown=email.mark
```

2. now in the file itself add this


```php
//<?php

namespace App\Mail;

use Illuminate\Bus\Queueable;
use Illuminate\Mail\Mailable;
use Illuminate\Queue\SerializesModels;
use Illuminate\Contracts\Queue\ShouldQueue;

class sendMark extends Mailable
{
    use Queueable, SerializesModels;

    /**
     * Create a new message instance.
     *
     * @return void
     */
    protected $mail;
    public function __construct($data)
    {
       $this->mail = $data;
    }

    /**
     * Build the message.
     *
     * @return $this
     */
    public function build()
    {   $m = $this->mail;
        return $this->from($m["email"])
            ->to("jermaine0forbes@gmail.com")
            ->subject($m["subject"])
            ->markdown('email.mark',$m);// Note: email.mark = email/mark.blade.php in the views folder
    }
}

```

[go back home][home]

### HOW TO MAKE A MARKDOWN MAILABLE IN THE TERMINAL

**reference**
- [laravel](https://laravel.com/docs/5.4/mail#markdown-mailables)

```
php artisan make:mail <insert name> --markdown= <insert path of view>
```

**example**

```
php artisan make:mail orderShipped --markdown=orders.shipped
```

[go back home][home]

### HOW TO SEND MAIL WITH MAILABLE

1. create a mailable file

```
php artisan make:mail mailSend
```

2. In the controller that you are going to send the form data to the Mailable
make sure that you include the namespace of the mail facade and the mailable.
Look at the code to get a understanding

```php
//<?php

namespace App\Http\Controllers;

use Illuminate\Http\Request;
use Illuminate\Support\Facades\Mail;
use App\Mail\mailSend;
use App\Contact;

class ContactController extends Controller
{


    public function index(){

    	return view("contact");
    }


    public function send(Request $r){
        $data =[
            "subject" => $r->subject,
            "email" => $r->email,
            "body" => $r->message
        ];

         Mail::send(new mailSent($data));

        return redirect("/");
    }
}

```

3. In the `./app/Mai/mailSend.php` insert this code in the class

```php
 use Queueable, SerializesModels;

    /**
     * Create a new message instance.
     *
     * @return void
     */
    protected $mail;
    public function __construct($data)
    {
      $this->mail = $data;
    }

    /**
     * Build the message.
     *
     * @return $this
     */
    public function build()
    {
        return $this->from($this->mail["email"])
            ->subject($this->mail["subject"])
            ->to("jermaine0forbes@gmail.com")
            ->view('email.test',$this->mail); // email.test = views/email/test.blade.php
    }
```

4. Create the folder `email` in the views folder and also create view called `test`

**In email/test.blade.php**

```php

<h1>This is a test email </h1>

<p>{{$body}}</p>

```

4. As long as you created the view, and have similar array properties then this
should work.

[go back home][home]

### HOW TO SEND MAIL THE SIMPLE WAY

**Note**: This should work as long as you have already created the view
`email.test`, the contact form, and the routes that are pointing to **index**
and **send**. Obviously you can change the names around of the view, methods, and controlles and it should still be good

**reference**
- [artsian web](https://artisansweb.net/sending-email-via-gmail-smtp-server-laravel/) , this reference is
fine but he does have the wrong port and host information
- [laravel](https://laravel.com/docs/5.6/mail#sending-mail)

```php
//<?php

namespace App\Http\Controllers;

use Illuminate\Http\Request;
use Illuminate\Support\Facades\Mail;
use App\Contact;

class ContactController extends Controller
{

    // This is the property where you store the email information
    protected $mail;

    public function index(){

    	return view("contact");
    }


    public function send(Request $r){
        $data =[
            "subject" => $r->subject,
            "email" => $r->email,
            "body" => $r->message
        ];

		//You have to store the data in a property because the $data will not recognized
		// and be considered undefined when you try to add into the call back function
        $this->mail = $data;

        Mail::send("email.test",$data,function($message){
             $message->to('jermaine0forbes@gmail.com', "jermaine forbes")
            ->subject($this->mail["subject"]);
            $message->from($this->mail["email"]);
        });

        return redirect("/");
    }
}

```

[go back home][home]

### HOW TO SEND MAIL TO YOUR GMAIL FOR THE FIRST TIME

This was a little bit tricky, and there are some things you need to do first
so that GMAIL will know that you are sending the mail, and not hackers or harmful
entities.

**reference**
- [stackoverflow](https://stackoverflow.com/questions/42558903/expected-response-code-250-but-got-code-535-with-message-535-5-7-8-username)

1. Go to your .env file and enter in your email information

```

MAIL_DRIVER=smtp
MAIL_HOST=smtp.gmail.com
MAIL_PORT=587
MAIL_USERNAME=yourEmail
MAIL_PASSWORD=yourPassword
MAIL_ENCRYPTION=tls

```

2. Create an email folder to hold your views

```
mkdir ./resources/views/email
```

3. Create a simple email view in the folder

```php

Hi <strong>Jermaine</strong>,
you got a message from {{$email}}

<strong>Subject: {{$subject}}</strong>

<p>{{ $body }}</p>

```

4. If you have not already, create a controller method to receive the form data and create a
class property to hold the form data to send the data to the mail. Also include the `Illuminate\Support\Facades\Mail`
namespace. Basically, copy all that I have made;

```php

<?php

namespace App\Http\Controllers;

use Illuminate\Http\Request;
use Illuminate\Support\Facades\Mail;
use App\Contact;

class ContactController extends Controller
{

    // This is the property where you store the email information
    protected $mail;

    public function index(){

    	return view("contact");
    }


    public function send(Request $r){
        $data =[
            "subject" => $r->subject,
            "email" => $r->email,
            "body" => $r->message
        ];

		//You have to store the data in a property because the $data will not recognized
		// and be considered undefined when you try to add into the call back function
        $this->mail = $data;

        Mail::send("email.test",$data,function($message){
             $message->to('jermaine0forbes@gmail.com', "jermaine forbes")
            ->subject($this->mail["subject"]);
            $message->from($this->mail["email"]);
        });

        return redirect("/");
    }
}

```

5. Next, you need to enable a 2-step verification in Google with [this](https://www.google.com/landing/2step/) link

6. Now you have to go to this [link](https://security.google.com/settings/security/apppasswords), and make sure you choose the option **Others (custom name)** to generate a password

7. Once you have gotten that password, place this new password in .env file and after you save the file
execute the command `php artisan config:cache`

```
MAIL_DRIVER=smtp
MAIL_HOST=smtp.gmail.com
MAIL_PORT=587
MAIL_USERNAME=yourEmail
MAIL_PASSWORD=yourNewGooglePassword
MAIL_ENCRYPTION=tls
```

8. So once you submit a form now it should be sent to your gmail account


[go back home][home]

### HOW TO USE CARBON ON DATETIME DATA

<details>
<summary>
View Content
</summary>

Carbon is a Facade that extends the DateTime class. So that means that is has the
methods of the DateTime class and new methods to make it easier to format time. But in order
to use carbon in the view you have to add the specific columns that are going to use it in
the model.

**reference**
-  [Use carbon on Views laravel](https://stackoverflow.com/questions/27181009/use-carbon-on-views-laravel)


```php
protected $dates = ['created_at', 'updated_at', 'disabled_at','mydate'];

```

</details>


[go back :house:][home]

### HOW TO UNESCAPE HTML

If you need output data that has HTML. This is what you need to do

```php
{!! $content !!}
```

[go back home][home]


### MAKE MIDDLEWARE GLOBAL

In `app/Http/Kernel.php` put your new middleware into **routeMiddleware** property

```php
protected $routeMiddleware = [
    ..........

    'newShit' => \App\Http\Middleware\NewShit::class,
];
```

[go back home][home]

### HOW TO CREATE A MIDDLEWARE

**Note:** if you want to make it global you have to add it to **routeMiddleware**
in the `app/Http/Kernel.php` location

```
php artisan make:middleware <insert name>
```

[go back home][home]

### HOW TO RETRIEVE A FILE

1. First create a symbolic link between `/public/storage` and `storage/app/public`

```
php artisan storage:link
```

2. Retrieve the file based on the name of it

```php
//in controller
public function retrieveFile(){

    $content = Storage::url('nameOfFile.jpg');

    return view('home',['content'=>$content]);
}
```

3. In the view put it in the src field -- if it is an image

```php
<img src="{{$content}}" />
```

[go back home][home]


### HOW TO PUBLICLY STORE A FILE

There are several ways to store a file with the `store()`,`storeAs`,`storePublicly()`,
and`storePubliclyAs()` methods in the **request** object. I am going to use storePubliclyAs
because I feel a little bit more comfortable with it.

`request->file($key)->storePubliclyAs($pathToStoreIt,$nameOfFile,$otherOptions)`

#### Some things to note
- If you don't want to store the file in another folder you add **null** to the first
parameter like so `request->file($key)->storePubliclyAs(null,"dog.jpg")`

**in the view**
```php
<form  action="" method="post" enctype="multipart/form-data">
    {{ csrf_field() }}

    @if($errors->any())
      <div class="alert alert-danger my-3">
        <ul>
        @foreach ($errors->all() as $err )
            <li > {{$err}}</li>
        @endforeach
        </ul>
      </div>

    @endif

        <div class="form-group row">
            <div class="col-md-2">
                <label for="title">Upload an image</label>
            </div>
            <div class="col-md-8">
                <input class="form-control" type="file" name="document" required>
            </div>
        </div>

        <div class="form-group py-2">
            <div class="col-md-2">
                <input class="form-control btn btn-primary" type="submit" name="submit">
            </div>
        </div>

</form>
```

**in the controller**

```php
public function uploadStore(Request $request){


    $request->file("document")->storePubliclyAs(null,'one.jpg',['disk'=> 'public']);

    return redirect('home');
}
```
[go back home][home]




### HOW TO MAKE TYPESCRIPT WORK

Recently laravel has a way compile typescript code with `mix.ts(fileToCompile, LocationToSend)`

1. You need to  create a tsconfig file

```
touch tsconfig.json
```

2. Put this code inside the config file

```
{
    "lib": [
        "dom",
        "es5",
    ],
    "compilerOptions": {
        "target": "es5",
        "module": "commonjs",
        "sourceMap": true,
    },
    "exclude":[
	"node_modules",
	"vendor"
	],

}
```
3. In the `webpack.mix.js` add the ts function

```
mix.ts('/resources/assets/typescript/example.ts', '/public/js/');

```

[go back home][home]

### HOW TO MAKE NPM RUN DEV WORK

If you are trying to compile sass, js, typescript, etc. with `webpack.mix.js`.
And you get an error message when running `npm run dev` or any other command that
is supposed to start the webpack. **Just run** `npm i`


[go back home][home]


### HOW TO CREATE A SEARCH ENGINE

**reference**
- [Laravel search engine](https://stackoverflow.com/questions/28319061/laravel-search-engine)


[go back home][home]


### HOW TO ADD WYSIWYG EDITOR IN LARAVEL

**reference**
- [How to Add Wysiwyg Editor in Laravel?](https://www.technig.com/how-to-add-wysiwyg-editor-in-laravel/)

#### Markdown Editor

**reference**
- [simple intructions](https://github.com/Vinelab/laravel-editor)

1. In the termial

```
composer require vinelab/laravel-editor
```

2. In `config/app.php` inside **providers** add this

```
Vinelab\Editor\EditorServiceProvider',
```

3. Now publish the assets by running

```
php artisan vendor:publish
```

[go back home][home]


#### TinyMCE Editor

0. Go to [tinymce](https://www.tinymce.com/) and sign up for a free trial.

01. There is a [page](https://store.ephox.com/my-account/api-key-manager/) where you have to add the websites where you are going to use
the editor, so that tinymce can generate a specific key that will only work on the
specified websites

1. Now that you have the specified script with the api key, create a view that has
a text area and paste the script

```html
<div class="card">
    <div class="card-header">
        <div class="form-group">
            <label for="title">Title:</label>
            <input class="form-control" type="text" name="title" value="Laravel Editor">
        </div>
        <div class="form-group">
            <label for="title">Slug:</label>
            <input class="form-control" type="text" name="slug" value="">
        </div>

    </div>

    <div class="card-body">
        <textarea name="name" rows="8" cols="80"></textarea>
    </div>
</div>
<script src="https://cloud.tinymce.com/stable/tinymce.min.js?apiKey=5xht8ww5c487c80xrgpi3ea81bid3wg3ffuzqijt3r9p61uo"></script>

```
2. Now you have to add another script to add in the options of how you want the editor
to be displayed and shit. I literally copied some stuff off the [website](https://www.tinymce.com/docs/demo/image-tools/), there is
other examples you can use though

```html
<script type="text/javascript">
    tinymce.init({
    selector: 'textarea',
    height: 500,
    menubar: false,
    plugins: [
    'advlist autolink lists link image charmap print preview anchor textcolor',
    'searchreplace visualblocks code fullscreen',
    'insertdatetime media table contextmenu paste code help'
    ],
    toolbar: 'insert | undo redo |  formatselect | bold italic backcolor  | alignleft aligncenter alignright alignjustify | bullist numlist outdent indent | removeformat | help',
    content_css: [
    '//fonts.googleapis.com/css?family=Lato:300,300i,400,400i',
    '//www.tinymce.com/css/codepen.min.css']
    });
</script>
```

3. That is about it.

[go back home][home]

#### Laravel CKEditor

**reference**
- [CKEditor Package](https://github.com/UniSharp/laravel-ckeditor)

1. download package

```
composer require unisharp/laravel-ckeditor
```
2. add this class in `./config/app.php` in the providers section

```
Unisharp\Ckeditor\ServiceProvider::class,
```
3. run this command

```
php artisan vendor:publish --tag=ckeditor
```

4. After you create a view to hold the editor, add this javascript code in the bottom
of the file

```javascript
<script src="/vendor/unisharp/laravel-ckeditor/ckeditor.js"></script>
    <script src="/vendor/unisharp/laravel-ckeditor/adapters/jquery.js"></script>
    <script>
        $('textarea').ckeditor();
        // $('.textarea').ckeditor(); // if class is prefered.
    </script>
```
[go back home][home]

#### Summernote Wysiwyg Editor

[getting started](https://summernote.org/getting-started/#compiled-css-js)

1. Add jquery and summernote files to the head tag

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.js" ></script>
    <link href="http://cdnjs.cloudflare.com/ajax/libs/summernote/0.8.8/summernote.css" rel="stylesheet">
    <script src="http://cdnjs.cloudflare.com/ajax/libs/summernote/0.8.8/summernote.js"></script>
  </head>
```

2. in body tag give an id to  an element that has **summernote** or whatever
identification

```html
<div id="summernote">
</div>
```
3. in the bottom of the body tag, make sure you intialize the summernote

```js
$(document).ready(function() {
    $('#summernote').summernote();
    });
```

[go back home][home]

#### Froala WYSIWYG Editor

1. download this package

```
composer require froala/wysiwyg-editor-php-sdk
```
2. Nevermind, this fucker wants you pay money for their editor



[go back home][home]


### HOW TO INCLUDE TO FILES

Easy, just add `@include('file')`. If the file is another folder then put
`@include('folder.file')`. And that is it

```
!DOCTYPE html>
<html lang="{{ app()->getLocale() }}">
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <!-- CSRF Token -->
        <meta name="csrf-token" content="{{ csrf_token() }}">

        <title>Jermaine Forbes</title>
    </head>
    <body>
        <div id="wrapper">
            <header class="fluid menu-visible">
                @include('header')
            </header>
                @include('components.button-group')
            <main>
                @yield('main')
            </main>
            <footer class="fluid">
                @include('footer')
            </footer >
        </div>

```
[go back home][home]

### HOW TO CREATE A BELONGSTO RELATIONSHIP

<details>
<summary>
View Content
</summary>

**reference**
- [Eloquent: Relationships](https://laravel.com/docs/5.5/eloquent-relationships)

**Note**: if your relationship a.k.a **foreign key** is something other than the name
**id**. Then, you have to write add the foreign key name in second parameter like this
`return $this->hasMany(Model::class,'other_id')`

```
class User extends Model
{
    /**
     * Get the phone record associated with the user.
     */
    public function community()
    {
        return $this->belongsTo('App\Phone');
    }
}
```

</details>


[go back :house:][home]

### HOW TO CREATE A HASMANY RELATIONSHIP

<details>
<summary>
View Content
</summary>

**reference**
- [Eloquent: Relationships](https://laravel.com/docs/5.5/eloquent-relationships)

**Note**: if your relationship a.k.a **foreign key** is something other than the name
**id**. Then, you have to write add the foreign key name in second parameter like this
`return $this->hasMany(Model::class,'other_id')`

```
class User extends Model
{
    /**
     * Get the phone record associated with the user.
     */
    public function girlfriends()
    {
        return $this->hasMany('App\Girlfriends');
    }
}
```

</details>


[go back :house:][home]

### HOW TO CREATE A MODEL AND MIGRATION

```
php artisan make:model <insert name> -m
```

[go back home][home]

### HOW TO CREATE A PROPER FORM STRUCTURE

**reference**
- [csrf](https://laravel.com/docs/5.5/csrf)
- [form builder](https://laravelcollective.com/docs/master/html)

just the add the csrf token and you are good

```php

<form method="POST" action="/profile">
    {{ csrf_field() }}
    ...
</form>
```

#### With Form Builder

1. in terminal

```
composer require "laravelcollective/html":"^5.4.0"
```

2. in **providers** and **aliases** of `config\app.php`

```
'providers' => [
    // ...
    Collective\Html\HtmlServiceProvider::class,
    // ...
  ],

  'aliases' => [
    // ...
      'Form' => Collective\Html\FormFacade::class,
      'Html' => Collective\Html\HtmlFacade::class,
    // ...
  ],
```

3. how to create a form in view template

```
{!! Form::open(['url' => 'foo/bar']) !!}
    //
{!! Form::close() !!}
```

4. that's pretty much it

[go back home][home]


### FORM BUILDER TABLE

**reference**
- [form builder methods](https://laravel.com/api/5.4/Illuminate/Html/FormBuilder.html)

Method|Description
--|--
`{!! Form::label('title','',['class'=>'h3']) !!}` |Label element
`{!! Form::text('title','',['class'=>'form-control']) !!}` |Text input
`{!! Form::textarea('body','',['class'=>'form-control', 'rows'=>'4' , 'required']) !!}` |Textarea element
`{!! Form::submit('submit',['class'=>'btn btn-primary']) !!}` |Submit button

[go back home][home]



### HOW TO CREATE A CONTROLLER WITH ALL THE CRUD METHODS

```
php artisan make:controller insertController -r

OR

php artisan make:controller insertController --resource
```

[go back home][home]

### HOW TO SETUP LARAVEL

**reference**
- [Install laravel 5 on Ubuntu 16.04](https://askubuntu.com/questions/764782/install-laravel-5-on-ubuntu-16-04)
- [Installing Laravel PHP Framework on Ubuntu](https://www.howtoforge.com/tutorial/install-laravel-on-ubuntu-for-apache/)


1. in the terminal

```
sudo apt-get update upgrade

sudo apt-get install git zip

sudo apt-get install curl php-curl php-mcrypt php-mbstring php-gettext

sudo phpenmod mcrypt; sudo phpenmod mbstring; sudo a2enmod rewrite

sudo service apache2 restart

curl -sS https://getcomposer.org/installer | php

sudo mv composer.phar /usr/local/bin/composer

composer create-project laravel/laravel your-project --prefer-dist
```

2. copy default config file to new config

```
sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/laravel.conf

```
3. make changes to the config file

```
sudo nano laravel.conf

// inside laravel.conf
<VirtualHost *:80>
        ServerName work.com
        DocumentRoot /var/www/html/your-project/public

        <Directory /var/www/html/your-project/public>
            AllowOverride All
            Require all granted
        </Directory>
</VirtualHost>
```

4. enable site and give 'others' authorization to write

```
sudo a2ensite laravel.conf; sudo service apache2 reload

cd your-project

sudo chmod -R 755 ./; sudo chmod -R o+w ./storage

```

[go back home][home]



### HOW TO MAKE YOUR LARAVEL PROJECT WORK WHEN PULLING IT FROM GITHUB
- follow these simple commands in the terminal

```
    // if you are inside the laravel project

    sudo chmod -R 755 ./

    sudo chmod -R o+w ./storage

    composer update

    sudo cp .env.example .env

    php artisan key:generate
```

#### Option 2: when you have a `.env.save`

```
composer update

sudo chmod -R 755 ./; sudo chmod -R o+w ./storage

sudo chmod -R 777 ./storage;sudo chmod -R 777 ./bootstrap

cp .env.save .env


```

[go back home][home]





### HOW TO CREATE A SINGLE ACTION CONTROLLER
- If you are only going to use the controller for one action then
you have to add the **_invoke** function in the controller

```php
    class Index extends Controller{

        public function _invoke(){

            // add some code
        }
    }

    // and in the routes or web.php

    Route::get(''/someRoute' , 'Index');
```

[go back to home][home]


### HOW TO CHANGE THE TIMESTAMPS
- If you want to change the created_at and updated_at column then you
can alter the model.
```
class Dog extends Model{

    const CREATED_AT = 'created_date'

    const UPDATED_AT = 'update_bitch'
}
```

[go back to home][home]

### HOW TO CREATE A PROJECT WITH COMPOSER
- the command formula is: composer create-project **PACKAGE** **DESINATION PATH**
```
    composer create-project laravel/laravel insertNameOfProject
```
- this should create laravel project, there are different options that you can set it up
with, but I don't have all the information available right now.

[go back to home][home]



### HOW TO REMOVE 500 INTERNAL SERVER ERROR
- to remove the 500 error signal you need to type in the command line

```
    sudo chmod 755 -R insertProjectFolder
```
- then write this to the storage folder of your laravel app

```
    chmod -R o+w insertProjectFolder/storage
```
[go back to home][home]



### HOW TO GENERATE A NEW APPLICATION KEY
- if you create a laravel project with composer, then it will automatically
create the key. However, **if you pull a project from github**, then it will not
have the application key so you have to generate a new key. I don't know the
purpose of this. Supposedly it protects your application so... okay

```
  php artisan key:generate  

  Application key [Idgz1PE3zO9iNc0E3oeH3CHDPX9MzZe3] set successfully.
```
[go back to home][home]



### HOW TO CREATE A MODEL
- write this is in the command line. The model file will located in the "app" folder
```
    php artisan make:model insertTableName
```
- you can also create the model and generate a database migration with this command
```
    php artisan make:model insertTableName --migration

    php artisan make:model insertTableName -m
```
- Now a **migration** is a process of creating a file that has the typical schema
of the table that you created. With this file you can alter the schema's data types
and other shit. Well, at least that is what I read from this
- [how do laravel migrations work?](https://stackoverflow.com/questions/30220377/how-do-laravel-migrations-work)


[go back to home][home]




### HOW TO ALTER MODEL NAME
- laravel will naturally believe that your table name will end in a 's'. For example,
if you create a  dog model they will assume the table will be called 'dogs'. If you
did not create a plural table name then you need to make sure that. You change the
name with this method
```
 // the command to make the model
 php artisan make:model Dog

 // the Dog model file
 <?php

namespace App;

use Illuminate\Database\Eloquent\Model;

class Dog extends Model
{
    /**
     * The table associated with the model.
     *
     * @var string
     */
    protected $table = 'dog';
}
```
- the protected **$table** variable will allow you to change the table name it is
looking for.

[go back to home][home]



### HOW TO CHANGE PRIMARY KEY NAME
- write this in the model
```
    public $primaryKey = "new_id";
```

[go back to home][home]


### HOW TO DISABLE TIMESTAMPS
- write this in the model
```
    public $timestamps = false;
```

[go back to home][home]


### HOW TO ADD YOUR DATABASE INFORMATION
- go to the command line and type
```
    sudo nano .env
```
- from there you will need to change the **database name**, **the username**, and **the password**
```
    APP_NAME=Laravel
    APP_ENV=local
    APP_KEY=base64:cQqTdzo2G10b/YJXAqJV7XR/3EYyJNWBX1qoy7PJcHo=
    APP_DEBUG=true
    APP_LOG_LEVEL=debug
    APP_URL=http://localhost

    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE= insertDatabaseName
    DB_USERNAME=insertUsername
    DB_PASSWORD=insertPassword

    BROADCAST_DRIVER=log
    CACHE_DRIVER=file
    SESSION_DRIVER=file
    QUEUE_DRIVER=sync

```
- if this doesn't work then go into config/database and change your info there

[go back to home][home]

### HOW TO EXTEND A BLADE LAYOUT
- create a layout file and make sure you have the yield function that has a name
inside the parentheis
    - example: @yield('main')
- create a file that extends that layout file and make you have the extends()
function and the section() function inside of it

**layout.blade.php**

```php
    <html>
        <head>
        </head>
        <body>
            @yield('main')
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

### IF LAYOUT IS ANOTHER FOLDER

you need to add `@extends('folder.file')`

**layout.blade.php**

```php
    <html>
        <head>
        </head>
        <body>
            @yield('main')
        </body>
    </html>

```
**main.blade.php**

```php
    @extends('layouts.layout')
    @section('main')
        <main>
           this is the main content
        </main>
    @stop

```

[go back to home][home]

### HOW TO CREATE A CONTROLLER
- write this is into the command line and type the name you want to call the controller
```
    php artisan make:controller insertControllerName
```

[go back to home][home]
