# Laravel How To

## Installation
- [how to create a project with composer][create-project]
- [how to remove 500 internal server error][500]
- [how to generate a new application key][new-key]

## Model
- [how to create a model][create-model]
- [how to alter the model name][name-model]
- [how to change primary key name][prime-name]
- [how to disable timestamps][timestamps]
- [how to add your database information][data-info]
- [how to change the created and updated timestamps][create-update]


## View
- [how to extend a blade layout][extend]

## Controller
- [how to create a controller][control]

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
[go back to home][home]

### HOW TO CREATE A CONTROLLER
- write this is into the command line and type the name you want to call the controller
```
    php artisan make:controller insertControllerName
```

[go back to home][home]
