# Laravel How To

## Installation
- [how to setup laravel][laravel]
- [how to create a project with composer][create-project]
- [how to remove 500 internal server error][500]
- [how to generate a new application key][new-key]
- [how to make your laravel project work when pulling it from github][pulling]

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

## Mix/Webpack
- [how to make 'npm run dev' work][mix-work]
- [how to make typescript work][typescript]

## View
- [how to extend a blade layout][extend]
- [how to include files ][include]
- [how to unescape html][html-unescape]

## Controller
- [how to create a controller][control]
- [how to create a single action controller][single-control]
- [how to create a controller with all the CRUD methods][crud-control]

## File Storage
- [how to publicly store a file][file-store-public]
- [how to retrieve a file][file-retrieve]


## Mail
- [how to send mail to your gmail for the first time][first-mail]
- [how to send mail the simple way][mail-simple]
- [how to send mail with Mailable][mailable]


## Middleware
- [how to create a middleware][middleware]
- [make middleware global][global-middleware]

## Form
- [how to create a proper form structure][form]
- [form builder table][form-table]

## Other
- [how to add wysiwyg editor in laravel][wysiwyg]
- [how to create a search engine][search-engine]

[mailable]:#how-to-send-mail-with-mailable
[mail-simple]:#how-to-send-mail-the-simple-way
[first-mail]:#how-to-send-mail-to-your-gmail-for-first-time
[carbon-meth]:#how-use-carbon-methods-on-datetime-data
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
[belongsTo]:#how-to-create-a-belongsTo-relationship
[hasMany]:#how-to-create-a-hasMany-relationship
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


### HOW TO SEND MAIL WITH MAILABLE

1. create a mailable file 

```
php artisan make:mail mailSend
```

2. In the controller that you are going to send the form data to the Mailable
make sure that you include the namespace of the mail facade and the mailable.
Look at the code to get a understanding 

```php
<?php

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
            ->view('email.test',$this->mail);
    }
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

[go back home][home]

### HOW TO SEND MAIL TO YOUR GMAIL FOR THE FIRST TIME 

This was a little bit tricky, and there are some things you need to do first 
so that GMAIL will know that you are sending the mail, and not hackers or harmful 
entities.

**reference**
- [stackoverflow](https://stackoverflow.com/questions/42558903/expected-response-code-250-but-got-code-535-with-message-535-5-7-8-username)

- Go to your .env file and enter in your email information

```

MAIL_DRIVER=smtp
MAIL_HOST=smtp.gmail.com
MAIL_PORT=587
MAIL_USERNAME=yourEmail
MAIL_PASSWORD=yourPassword
MAIL_ENCRYPTION=tls

```

- Create an email folder to hold your views

```
mkdir ./resources/views/email
```

- Create a simple email view in the folder

```php

Hi <strong>Jermaine</strong>,
you got a message from {{$email}}

<strong>Subject: {{$subject}}</strong>

<p>{{ $body }}</p>

```

- If you have not already, create a controller method to receive the form data and create a 
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

- Next, you need to enable a 2-step verification in Google with [this](https://www.google.com/landing/2step/) link

- Now you have to go to this [link](https://security.google.com/settings/security/apppasswords), and make sure you choose the option **Others (custom name)** to generate a password

- Once you have gotten that password, place this new password in .env file and after you save the file 
execute the command `php artisan config:cache`

```
MAIL_DRIVER=smtp
MAIL_HOST=smtp.gmail.com
MAIL_PORT=587
MAIL_USERNAME=yourEmail
MAIL_PASSWORD=yourNewGooglePassword
MAIL_ENCRYPTION=tls
```

- So once you submit a form now it should be sent to your gmail account


[go back home][home]

### HOW TO USE CARBON ON DATETIME DATA 

Carbon is a Facade that extends the DateTime class. So that means that is has the 
methods of the DateTime class and new methods to make it easier to format time. But in order 
to use carbon in the view you have to add the specific columns that are going to use it in 
the model.

**reference**
-  [Use carbon on Views laravel](https://stackoverflow.com/questions/27181009/use-carbon-on-views-laravel)


```php
protected $dates = ['created_at', 'updated_at', 'disabled_at','mydate'];

```

[go back home][home]

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
php artisan create:middleware <insert name>
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
<div style="color:white; text-align:center; text-transform:uppercase; background:teal; width:200px; padding:1em;">
[go back home][home]
</div>



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

[go back home][home]

### HOW TO CREATE A HASMANY RELATIONSHIP

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

[go back home][home]

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
[go back home][home]



### HOW TO CREATE AUTHENTICATION


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

    const $CREATED_AT = 'created_date'

    const $UPDATED_AT = 'update_bitch'
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

### IF LAYOUT IS ANOTHER FOLDER

you need to add `@extends('folder.file')`

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
