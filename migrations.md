# migrations

What is a migration? Essentially, it is file that you create schema for a new table
that you want in the database. If the table already exists, then it will not be
create when you enter in the command **php artisan migrate**

- [how to create an existing table with migration][ex-table]
- [view all schema options][schema]
- [how to create a migration to create a new table][new-table]
- [how to create a migration file][create]
- [how to start a migration][start]

[ex-table]:#how-to-create-an-existing-table-with-migration
[schema]:#view-all-schema-options
[new-table]:#how-to-create-a-migration-to-create-a-new-table
[home]:#migrations
[create]:#how-to-create-a-migration-file
[start]:#how-to-start-a-migration

### how to create an existing table with migration

**reference**
- [migrations](https://laravel.com/docs/5.5/migrations)

```
    php artisan make:migrations create_users_table --table=users
```

[go back home][home]


### view all schema options
I might create my own table to I don't have to use the link. But I am too lazy to
do it right now

**reference**
- [schema table](https://laravel.com/docs/4.2/schema)

Command|Description
--|--
`$table->bigIncrements('id')`|Incrementing ID using a "big integer" equivalent.
`$table->date('created_at')`|DATE equivalent to the table
`$table->increments('id')` | Incrementing ID to the table (primary key).
`$table->integer('votes')` | INTEGER equivalent to the table
`$table->dateTime('created_at');` | DATETIME equivalent to the table
`$table->decimal('amount', 5, 2);` | DECIMAL equivalent with a precision and scale
`$table->timestamps();` | Adds created_at and updated_at columns
`$table->text('description');` | TEXT equivalent to the table
`$table->string('name', 100);` | VARCHAR equivalent with a length
`$table->enum('level', ['easy', 'hard']);` | ENUM equivalent column.
`$table->ipAddress('visitor');` | IP address equivalent column.

[go back to home][home]


### how to create a migration to create a new table
- this creates a file in the **database** folder that allows you to customize a schema
for a table
```
    php artisan make:migration create_users_table --create=users
```
[go back to home][home]


### how to create a migration file
- this creates a file in the **database** folder that allows you to customize a schema
for a table
```
    php artisan make:migration create_users_table
```
[go back to home][home]

### how to start a migration
- this will create the table in the database
```
  php artisan migrate
```

[go back to home][home]
