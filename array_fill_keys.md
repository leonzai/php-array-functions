```php
array_fill_keys ( array $keys , mixed $value ) : array
```
1. 非法键名将强制转化为字符串

```php
<?php
$keys = array('foo', 5, 10, 'bar');
$a = array_fill_keys($keys, 'banana');
print_r($a);

/*
Array
(
    [foo] => banana
    [5] => banana
    [10] => banana
    [bar] => banana
)
*/
```