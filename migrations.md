# migrations

What is a migration? Essentially, it is file that you create schema for a new table
that you want in the database. If the table already exists, then it will not be
create when you enter in the command **php artisan migrate**

- [how to create a migration file][create]
- [how to start a migration][start]


[home]:#migrations
[create]:#how-to-create-a-migration-file
[start]:#how-to-start-a-migration


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
