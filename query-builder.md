# Query Builder


- [how to use the select command][select]
- [how to use the limit command][limit]

[home]:#query-builder
[select]:#how-to-use-the-select-command
[limit]:#how-to-use-the-limit-command

### how to use the select command


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

### how to use the limit command

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
