# migrations

What is a migration? Essentially, it is file that you create schema for a new table
that you want in the database. If the table already exists, then it will not be
create when you enter in the command **php artisan migrate**


## Create
- [how to create a migration file][create]
- [how to create a migration to create a new table][new-table]
- [view all schema options][schema]
- [how to start a migration][start]
## Edit
- [how to create an existing table with migration][ex-table]
- [how to add a column to an existing table][add-col]
- [how to refresh a migration][refresh-table]

## Remove
- [how to remove seed data from tables][rm-seed]






[refresh-table]:#how-to-refresh-a-migration
[rm-seed]:#how-to-remove-seed-data-from-tables
[add-col]:#how-to-add-a-column-to-an-existing-table
[ex-table]:#how-to-create-an-existing-table-with-migration
[schema]:#view-all-schema-options
[new-table]:#how-to-create-a-migration-to-create-a-new-table
[home]:#migrations
[create]:#how-to-create-a-migration-file
[start]:#how-to-start-a-migration


### how to refresh a migration

<details>
<summary>
View Content
</summary>

:link: **Reference**
- [Rolling Back Migrations](https://laravel.com/docs/6.x/migrations#rolling-back-migrations)
---

:exclamation: **Note:** this will remove any columns from the migrations and then
add the columns back into the table. **This is perfect for** adding additional columns
to the table

---

```php
Schema::table('users', function (Blueprint $table) {
    $table->enum('sex',["male","female"]);
    $table->enum('plan',["free","monthly","annual"]);// added a new column to the schema
    $table->string("race",15);
});
```

```
php artisan migrate:refresh --path=./path/to/file
```

#### If you are only trying to refresh one migration file

1. In the migration file comment out the dropColum methods if the columns are not
in the table anymore

```php
public function down()
{
    Schema::table('users', function(Blueprint $table){
      // $table->dropColumn('sex');
      // $table->dropColumn("race");
      // $table->dropColumn('plan');
    });
}

```

2. Do the migration, and add the **path** flag to the command

```
 php artisan migrate:refresh  --path=./path/to/file

```


</details>

[go back :house:][home]


### how to remove seed data from tables

<details>
<summary>
View Content
</summary>

:link: **Reference**
- [laravel seed rollback after seeded to database](https://stackoverflow.com/questions/44729769/laravel-seed-rollback-after-seeded-to-database)
---
:exclamation: **Note:** If you seeded data and you remove all the data from table
this is the best way to do it.

```
php artisan migrate:refresh --seed
```

</details>

[go back :house:][home]


### how to add a column to an existing table

<details>
<summary>
View Content
</summary>

:link: **Reference**
- [Add a new column to existing table in a migration](https://stackoverflow.com/questions/16791613/add-a-new-column-to-existing-table-in-a-migration)
---
1. First make a migration file

```
php artisan make:migration add_col_user --table=users
```

2. Now, move the migration file to a new folder so that you can only migrate that
specific file

```
mkdir ./database/migrations/add_columns

mv ./database/migrations/add_col_user.php  ./database/migrations/add_columns/add_col_user.php
```

3. Open up the file and add any columns to the table. **Note** remove the **create**
static method and replace it with the **table** method

```php
public function up()
{   // this will add two columns to the table called sex and race
    Schema::table('users', function (Blueprint $table) {
        $table->enum('sex',["male","female"]);
        $table->string("race",25);
    });
}

```

4. Finally, do a migration to that specific folder

```
php artisan migrate  --path=./database/migrations/add_columns
```
5. And that should add the columns to the table

</details>

[go back :house:][home]

### how to create an existing table with migration

**reference**
- [migrations](https://laravel.com/docs/5.5/migrations)

```
    php artisan make:migration create_users_table --table=users
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
