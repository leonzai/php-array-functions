```php
array_unshift ( array &$array [, mixed $... ] ) : int
```

1. 该函数返回追加后数组的长度。
2. 7.3 开始可以只传递一个参数，只有一个参数时，对数组不作任何改变，返回数组长度。
3. 数组的数字索引从 0 开始重新索引，字符串索引不变。

```php
<?php
$queue = ["a", "b"];
array_unshift($queue, "c", "d");
print_r($queue);

/*
Array
(
    [0] => c
    [1] => d
    [2] => a
    [3] => b
)
*/
```