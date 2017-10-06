# Query Builder

- [all query builder options][all]
- [how to shorten the name of the model path][alias]
- [how to use the select method][select]
- [how to use the limit method][limit]
- [how to use the first method][first]
- [how to retrieve one value from a table][value]
- [how to retrieve all the columns and rows from a table][all]
- [how to retrieve a row by its primary key][find]
- [how to create data][create]

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

### all query builder options
Here is the link to see all of the different commands. Or at least the most common
ones.

**reference**
- [query builder](https://laravel.com/docs/4.2/queries)

[go back home][home]


### how to create data
```
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


```
	use App\pokemon as poke;

	$result = poke::select('name','type')->get();
```

```
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
