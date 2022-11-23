```php
array_intersect_key ( array $array1 , array $array2 [, array $... ] ) : array
```

1. 比较采用规则：if (string) $elem1 === (string) $elem2

```php
<?php
$array1 = array('blue'  => 1, 'red'  => 2, 'green'  => 3, 'purple' => 4);
$array2 = array('green' => 5, 'blue' => 6, 'yellow' => 7, 'cyan'   => 8);

var_dump(array_intersect_key($array1, $array2));

/*
array(2) {
  ["blue"]=>
  int(1)
  ["green"]=>
  int(3)
}
*/
```