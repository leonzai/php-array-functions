```php
array_intersect_assoc ( array $array1 , array $array2 [, array $... ] ) : array
```

1. 键名和值比较都采用规则：if (string) $elem1 === (string) $elem2，如果键名不相等，不会转换和比较值。

```php
<?php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red", &#039;name&#039; => "");
$array2 = array("a" => "green", "b" => "yellow", "blue", "red", "name" => false);
$result = array_intersect_assoc($array1, $array2);
var_dump($result);

/*
array(2) {
  ["a"]=>
  string(5) "green"
  ["name"]=>
  string(0) ""
}
*/
```