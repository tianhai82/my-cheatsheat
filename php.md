1. PHP Syntax
- Pure php file do not need `?>`
- statement needs to end with semicolon
- variable: `$name = "Peter";`
- string concatenation: `$msg = "Hello. " . "Welcome to PHP!";`
	- `$name .= " is a handsome guy";`
- reference operator (&)
```php
	$var1 = 5;
	$var2 = &$var1;
	$var1 = 6;
	echo $var2;
	// Output: 6
```
- power: `$n = 4 ** 2;` // 16
- to access global variable in a function, call `global $x` first. Or use super `$GLOBALs["x"]`
- array
```php
$string_array = ["first element", "second element"];
$string_array[] = "third element"; //appending to array
print_r($string_array) // output array in human readable form
array_push($string_array, "four"); // append to array
count($string_array) // returns num of elements in array

$some_numbers = ["1", 2, "three"];
echo array_pop($some_numbers); // "three"

array_unshift($joke, "Why is 6", "afraid of 7?", "Because") // add elements to front of array

$pieces = [1, "2", "three", 4.0];
$glue = " and a ";
echo implode($glue, $pieces); // join $pieces with $glue in between to output a string

array_shift($some_numbers); // remove and return first element
```

- Associative Array (*+* operator will not overwrite existing keys)
```php
$my_array = ["panda" => "very cute", "lizard" => "cute", "cockroach" => "not very cute"];
$more_rankings = ["capybara" => "cutest", "lizard" => "not cute", "dog" => "max cuteness"];
$animal_rankings = $my_array + $more_rankings;
unset($animal_rankings["capybara"]); // Removes the "capybara" element
```

- if elseif else
```php
if ($fav_fruit === "banana"){
  echo "Enjoy the banana!";
} elseif ($fav_fruit === "apple"){
  echo "Enjoy the apple!";
} elseif ($fav_fruit === "orange"){
  echo "Enjoy the orange!";
} else {
  echo "Enjoy the fruit!";
}
```	

- for each
```php
foreach ($array as $key => $value) {
  // code block
}
```

- constants
```php
define("HTTP_Status", "200"); //define constant
defined("HTTP_STATUS"); // check whether constant is already defined
const HTTP_STATUS = "200";
```

- variable variable (create variable dynamically)
```php
$foo = "bar";
$$foo = "baz";

echo $bar; // "baz"
```

- types
```php
$completed = true;
gettype($completed); // boolean
```
