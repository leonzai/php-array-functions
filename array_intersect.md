```php
array_intersect ( array $array1 , array $array2 [, array $... ] ) : array
```

```php
<?php
$array1 = array("a" => "green", "red", "blue");
$array2 = array("b" => "green", "yellow", "red");
$result = array_intersect($array1, $array2);

var_dump($result);

/*
array(2) {
  ["a"]=>
  string(5) "green"
  [0]=>
  string(3) "red"
}
*/

<?php
$array1 = array("a" => "green", "green", "blue");
$array2 = array("b" => "green", "yellow", "red");
$result = array_intersect($array1, $array2);

var_dump($result);

/*
array(2) {
  ["a"]=>
  string(5) "green"
  [0]=>
  string(5) "green"
}
*/
```
