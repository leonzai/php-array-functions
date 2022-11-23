```php
prev ( array &amp;$array ) : mixed
```

1. 如果数组是空数组或者指针超出了数组的范围，函数返回 false。
2. 想要判断返回 false 的时候是值还是超出了数组的范围（或是空数组），请配合 `key()` 使用，如果此函数返回 false 并且 `key()` 返回 NULL，此时才可以确定超出了数组的长度（或是空数组）。

```php
&lt;?php
$transport = [&#039;foot&#039;, &#039;bike&#039;, &#039;car&#039;, &#039;plane&#039;];
$mode = current($transport); // $mode = &#039;foot&#039;;
$mode = next($transport);    // $mode = &#039;bike&#039;;
$mode = current($transport); // $mode = &#039;bike&#039;;
$mode = prev($transport);    // $mode = &#039;foot&#039;;
$mode = end($transport);     // $mode = &#039;plane&#039;;
$mode = current($transport); // $mode = &#039;plane&#039;;

$arr = array();
var_dump(current($arr)); // bool(false)

$arr = array(array());
var_dump(current($arr)); // array(0) { }
```