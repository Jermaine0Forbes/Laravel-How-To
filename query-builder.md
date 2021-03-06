# Query Builder

## Create
- [how to create data][create]
## Edit
- [how to update data][update]
## Delete
- [how to delete a row by id][delete-id]

## Methods
- [all query builder options][all]
- [how to retrieve one value from a table][value]

- [how to check if a record or data exists][data-exists]
- [how to shorten the name of the model path][alias]
- [how to use the select method][select]
- [how to use the limit method][limit]
- [how to use the first method][first]

- [how to retrieve all the columns and rows from a table][all]
- [how to retrieve a row by its primary key][find]

- [how to group data by a column][groupBy]
- [how to alias a table][alias-table]
- [how to concat two columns][concat-columns]
- [how to check if collection is empty][is-empty]
- [how to get value instead of array][get-value]

- [how to check if data exists][data-exists]

[data-exists]:#how-to-check-if-data-exists
[get-value]:#how-to-get-value-instead-of-array
[is-empty]:#how-to-check-if-collection-is-empty
[concat-columns]:#how-to-concat-two-columns
[alias-table]:#how-to-alias-a-table
[update]:#how-to-update-data
[delete-id]:#how-to-delete-a-row-by-id
[data-exists]:#how-to-check-if-a-record-or-data-exists
[groupBy]:#how-to-group-data-by-a-column
[all]:#all-query-builder-options
[home]:#query-builder
[select]:#how-to-use-the-select-method
[limit]:#how-to-use-the-limit-method
[first]:#how-to-use-the-first-method
[value]:#how-to-retrieve-one-value-from-a-table
[alias]:#how-to-shorten-the-name-of-model-path
[all]:#how-to-retrieve-all-the-columns-and-rows-from-a-table
[find]:#how-to-retrieve-a-row-by-its-primary-key
[create]:#how-to-create-data



### how to check if data exists

<details>
<summary>
View Content
</summary>

:link: **Reference**

- [Laravel Eloquent exists() and doesntExist() Example](https://www.itsolutionstuff.com/post/laravel-eloquent-exists-and-doesntexist-exampleexample.html)
---


```php
 public function index()
    {
        $isExist = User::select("*")
                        ->where("email", "yemmerich@example.net")
                        ->exists();
   
        if ($isExist) {
            dd('Record is available.');
        }else{
            dd('Record is not available.');
        }
  
    }

```

</details>

[go back :house:][home]


### how to get value instead of array

<details>
<summary>
View Content
</summary>

:link: **Reference**
- [stackoverflow](https://stackoverflow.com/questions/34405138/laravel-5-2-pluck-method-returns-array)
---

```php
  DB::table('users')->where('id', 1)->value('name');
```

</details>

[go back :house:][home]


### how to check if collection is empty

<details>
<summary>
View Content
</summary>

:link: **Reference**

- [stackoverflow](https://stackoverflow.com/questions/35839303/laravel-check-if-collection-is-empty)
---

Here are a couple of ways to check if the collection is empty

```php

// first way
if ($mentor->first()) { } 

// second way
if ($mentor->isEmpty()) { }

// third way
if ($mentor->count()) { }
```

</details>

[go back :house:][home]



### how to concat two columns

<details>
<summary>
View Content
</summary>

- [Laravel concat two columns with example](https://www.itsolutionstuff.com/post/laravel-concat-two-columns-with-exampleexample.html)

#### example 1 

when doing a query you use an alias and concat the two values

```php
/**
 * Show the application dashboard.
 *
 * @return \Illuminate\Http\Response
 */
public function index()
{
    $users = User::select("*", DB::raw("CONCAT(users.first_name,' ',users.last_name) as full_name"))
        ->get();
  
    return view('home', compact('users'));
}
```

#### example 2

create a method withihn the model, so when you do a query for that model. That attribute will be printed out

```php

  class User extends Model{

    /**
    * Get the user's full concatenated name.
    * -- Must postfix the word 'Attribute' to the function name
    *
    * @return string
    */
    public function getFullNameAttribute()
    {
        return "{$this->first_name} {$this->last_name}";
    }
  }
```

```php
  <span>{$user->full_name}</span>
```

</details>


[go back :house:][home]


### how to alias a table

<details>
<summary>
View Content
</summary>

- [stackoverflow](https://stackoverflow.com/questions/17713730/how-to-alias-a-table-in-laravel-eloquent-queries-or-using-query-builder)

```php
$users = DB::table('really_long_table_name AS t')
           ->select('t.id AS uid')
           ->get();
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



### how to delete a row by id

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


### how to check if a record or data exists

**reference**
- [Laravel checking if record exists](https://stackoverflow.com/questions/27095090/laravel-checking-if-record-exists)

#### Example 1: 

```php
if (User::where('email', '=', Input::get('email'))->exists()) {
   // user found
}
```

#### Example 2: 

```php
if($role == "Ceertif Control Admin" && Auth::user()->admin()->exists()){
            $projectMonth = Auth::user()->admin()->client()->lots()->lotControls()->selectRaw(" COUNT(status) as status")->whereBetween("created_at", [$startMonth, $endMonth])->groupBy("status")->get();
            $projectYear =  Auth::user()->admin()->client()->lots()->lotControls()->selectRaw(" COUNT(status) as status")->whereBetween("created_at", [$startYear, $endYear])->groupBy("status")->get();
        }
```

#### Example 3: 

```php
$isExist = User::select("*")
	->where("email", "yemmerich@example.net")
	->exists();
```

[go back home][home]

### how to group data by a column

**reference**
- [Laravel groupBy column](https://stackoverflow.com/questions/32978842/laravel-group-by-date-to-month-only-and-get-count)

Let's look at this table for a second
```

+----+------------+---------+-----+--------+---------+-------+------------+
| id | name       | type    | hp  | attack | defense | speed | trainer_id |
+----+------------+---------+-----+--------+---------+-------+------------+
|  1 | ghastly    | ghost   |  30 |     35 |      30 |    80 |          1 |
|  2 | bulbasaur  | grass   | 110 |     65 |      85 |    27 |          2 |
|  3 | weedle     | bug     |  75 |     87 |      35 |    50 |          3 |
|  4 | abra       | psychic |  85 |     45 |      90 |    60 |          4 |
|  5 | charmander | fire    | 100 |    130 |      56 |    46 |          1 |
|  6 | psyduck    | water   |  90 |     75 |      66 |    33 |          3 |
|  7 | ekans      | poison  |  35 |     60 |      44 |    55 |          4 |
|  8 | geodude    | rock    |  40 |     80 |     100 |    20 |          5 |
|  9 | staryu     | water   |  30 |     45 |      55 |    85 |          3 |
| 10 | dragonair  | dragon  |  61 |     84 |      65 |    70 |          2 |
+----+------------+---------+-----+--------+---------+-------+------------+

```

There are multiple pokemon with similar trainers/trainer_id .  So lets say that I want
to group the pokemon together based on the trainer ID.  I would do this in the controller

```php

//<?php

use App\Pokemon;
class PokemonController extends Controller{

	public function index(){
		$pokemon = Pokemon::get->groupBy(function($data){
			return $data->trainer_id;
		});

		return view('home',"pokemon"=>$pokemon);
	}
}

```

This is what it looks like if you use the method `dd`. It will show you how the
pokemon have been grouped based on the trainer_id 1-5.
```
Collection {#187 ▼
  #items: array:5 [▼
    1 => Collection {#178 ▼
      #items: array:2 [▼
        0 => pokemon {#193 ▶}
        1 => pokemon {#197 ▶}
      ]
    }
    2 => Collection {#177 ▼
      #items: array:2 [▼
        0 => pokemon {#194 ▶}
        1 => pokemon {#202 ▶}
      ]
    }
    3 => Collection {#190 ▼
      #items: array:3 [▼
        0 => pokemon {#195 ▶}
        1 => pokemon {#198 ▶}
        2 => pokemon {#201 ▶}
      ]
    }
    4 => Collection {#189 ▼
      #items: array:2 [▼
        0 => pokemon {#196 ▶}
        1 => pokemon {#199 ▶}
      ]
    }
    5 => Collection {#188 ▼
      #items: array:1 [▶]
    }
  ]
}
```

[go back home][home]

### all query builder options
Here is the link to see all of the different commands. Or at least the most common
ones.

**reference**
- [query builder 4.2](https://laravel.com/docs/4.2/queries)
- [query builder 5.5](https://laravel.com/docs/4.2/queries)

#### Select

Commands|Description
--|--
`$users = DB::table('users')->get();`|Retrieving all rows from a table
`$users = DB::table('users')->select('name')->get();` |Retrieving all names
`$users = DB::table('users')->select('name as user_name')->get();` |Retrieving all names as user_name
`$users = DB::table('users')->select('name' , 'email', 'sex')->get();` |Retrieving all rows that have name, email, and sex
`$query = DB::table('users')->select('name');$users = $query->addSelect('age')->get();` |Adding a select clause to an existing query
`$users = Users::selectRaw('account * ? as price_with_tax', [1.0825])->get();` |Making a raw SQL query


#### Where

Commands|Description
--|--
`$user = DB::table('users')->where('name', 'John')->first();` |Retrieving a single row from a table
`$name = DB::table('users')->where('name', 'John')->pluck('name');` |Retrieving a single column from a row
`$email = DB::table('users')->where('name', 'John')->value('email');` |Retrieving a value from one column

#### Numbers

Commands|Description
--|--
`$users = DB::table('users')->count();` |Retrieves the total number of columns
`$price = DB::table('price')->max();` |Retrieves the max value of a column
`$price = DB::table('price')->sum();` |Retrieves the total sum of a column

#### Date

Commands|Description
--|--
`$price = DB::table('price')->all()->last();` |Retrieves the most recent column
`$price = DB::table('price')->latest()->first();` |Retrieves the most recent column
`$price = DB::table('price')->first();` |Retrieves the oldest column

#### Order

Commands|Description
--|--
`$users = DB::table('users')->orderBy('name', 'desc')->get();` |Retrieves rows in descending order
`$users = DB::table('users')->select("name")->latest()->get();` |Retrieves rows in descending order


##### JSON
Commands|Description
--|--
`$users = DB::table('users')->limit(15)->get()->toJson;` |Retrieves 15 users and turns the data to a JSON format


[go back home][home]


### how to create data
```php
	public function insert(Request $req){
		$pokemon = new poke;

		$pokemon->name = $req->name;

		$pokemon->save();

	}
```

[go back to home][home]

### how to retrieve a row by its primary key
- how to grab 1 key
```
	//grabs the row with the primary key of 1
    $result = poke::find(1);
```
- how to grab multiple keys
```
	//grabs the row with the primary key of 1, 2, 3
    $result = poke::find([1,2,3]);
```

[go back to home][home]

### how to retrieve all the columns and rows from a table
- its pretty easy
```
    $result = poke::all();
```

[go back to home][home]

### how to shorten the name of the model path
- the mode path is actually a namespace, but I probably wouldn't know what
that is when I look at this later. In any case, you can shorten the name by
giving it an **alias**, so like you will see in the code

```
	use App\pokemon as poke
```
- so now you can query data with is shortened representation of a table

```
	$result = poke::select('name','attack','defense')->where('type','water')->get();
```

[go back home][home]


### how to retrieve one value from a table
-  If you want to retrieve a single value from a row
you do it like this
```
	$result = poke::where('name','charmander')->value('attack');

```
[go back home][home]

### how to use the first method
- the first method grabs the first row of the specified columns
- **WARNING** you can only use the first method with the table method
you cannot use it with the model

```
	$result = DB::table('pokemon')->select('name','hp')->first();

```
[go back home][home]


### how to use the select method


```php
	use App\pokemon as poke;

	$result = poke::select('name','type')->get();
```

```php
	// if you have no model
	use Illuminate\Support\Facades\DB as DB;

	$result = DB::table('pokemon')->select('name','type')->get();
```

[go back home][home]

### how to use the limit method

```
	use App\pokemon as poke;

	$result = poke::select('name','type')->limit(5)->get();
```

```
	// if you have no model
	use Illuminate\Support\Facades\DB as DB;

	$result = DB::table('pokemon')->select('name','type')->limit(5)->get();
```

[go back home][home]
