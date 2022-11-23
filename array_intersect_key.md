```php
array_intersect_key ( array $array1 , array $array2 [, array $... ] ) : array
```

1. 比较采用规则：if (string) $elem1 === (string) $elem2

```php
<?php
$array1 = array(&#039;blue&#039;  => 1, &#039;red&#039;  => 2, &#039;green&#039;  => 3, &#039;purple&#039; => 4);
$array2 = array(&#039;green&#039; => 5, &#039;blue&#039; => 6, &#039;yellow&#039; => 7, &#039;cyan&#039;   => 8);

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