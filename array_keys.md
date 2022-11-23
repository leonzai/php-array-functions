```php
array_keys ( array $array ) : array

array_keys ( array $array , mixed $search_value [, bool $strict = FALSE ] ) : array


// $array：需要处理的数组
// $search_value：数组中值等于 $search_value 的键名都返回出来
// $preserve_keys：默认是 false，如果是 true，在比较 $search_value 时采用全等
```

```php
<?php
$array = ["blue", "red", 1, "1", "blue"];
print_r(array_keys($array, "1", true));

$array = ["blue", "red", ["green"], "blue", "blue"];
print_r(array_keys($array, ['green']));

/*
Array
(
    [0] => 3
)
Array
(
    [0] => 2
)
*/
```
