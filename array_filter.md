```php
array_filter ( array $array [, callable $callback [, int $flag = 0 ]] ) : array
```
1. 一次将每个元素传递给回调函数 $callback，函数返回 true，则当前元素会被放到返回的数组中。
2. $flag 默认是 0，表示把元素的值传递给回调函数。ARRAY_FILTER_USE_KEY 表示只传递键名，ARRAY_FILTER_USE_BOTH 将键值对都传递给回调函数。
3. 不要在回调函数中改变数组。

```php
<?php

$entry = [
    0 => 'foo',
    1 => false,
    2 => -1,
    3 => null,
    4 => '',
    5 => '0',
    6 => 0,
];

print_r(array_filter($entry));

/*
Array
(
    [0] => foo
    [2] => -1
)
*/
```

```php
<?php

$arr = ['a' => 1, 'b' => 2, 'c' => 3, 'd' => 4];

var_dump(array_filter($arr, function ($k) {
    return $k == 'b';
}, ARRAY_FILTER_USE_KEY));

var_dump(array_filter($arr, function ($v, $k) {
    return $k == 'b' || $v == 4;
}, ARRAY_FILTER_USE_BOTH));

/*
array(1) {
  ["b"]=>
  int(2)
}
array(2) {
  ["b"]=>
  int(2)
  ["d"]=>
  int(4)
}
*/
```

```php
<?php
function odd($var)
{
    return $var & 1;
}

function even($var)
{
    return !($var & 1);
}

$array1 = ['a' => 1, 'b' => 2, 'c' => 3, 'd' => 4, 'e' => 5];
$array2 = [6, 7, 8, 9, 10, 11, 12];

print_r(array_filter($array1, "odd"));

print_r(array_filter($array2, "even"));

/*
Array
(
    [a] => 1
    [c] => 3
    [e] => 5
)
Array
(
    [0] => 6
    [2] => 8
    [4] => 10
    [6] => 12
)
*/
```