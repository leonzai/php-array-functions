```php
prev ( array &$array ) : mixed
```

1. 如果数组是空数组或者指针超出了数组的范围，函数返回 false。
2. 想要判断返回 false 的时候是值还是超出了数组的范围（或是空数组），请配合 `key()` 使用，如果此函数返回 false 并且 `key()` 返回 NULL，此时才可以确定超出了数组的长度（或是空数组）。

```php
<?php
$transport = ['foot', 'bike', 'car', 'plane'];
$mode = current($transport); // $mode = 'foot';
$mode = next($transport);    // $mode = 'bike';
$mode = current($transport); // $mode = 'bike';
$mode = prev($transport);    // $mode = 'foot';
$mode = end($transport);     // $mode = 'plane';
$mode = current($transport); // $mode = 'plane';

$arr = array();
var_dump(current($arr)); // bool(false)

$arr = array(array());
var_dump(current($arr)); // array(0) { }
```