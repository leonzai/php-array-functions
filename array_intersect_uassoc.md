```php
array_intersect_uassoc ( array $array1 , array $array2 [, array $... ], callable $key_compare_func ) : array
```

内部原理：
1. 首先按照自定义的回调函数进行排序 
2. 第二个数组第一个元素开始和第一个数组的元素集合依次比较
3. 比较的是键，使用自定义函数进行比较，如果相等并且值也相等则这个元素被放置到返回数组中，否则继续比较。
4. 比较的时候如果键相等，不管值是否相等，就开始下次循环比较，下次循环比较会从第一个数组的下个元素开始比较（因为排序过，前面的不用比，肯定不相等）。

```php
<?php
$array1 = array("d" => "GREEN", "e" => "brown", "f" => 12);
$array2 = array("e" => "green", "f" => "brown", "g" => "GREEN");

print_r(array_intersect_uassoc($array1, $array2, function ($a, $b) {
    echo($a . " === " . $b . "\n");
    if ($a == $b) return 0;
    if ($a > $b) return 1;
    return -1;
}));

/*
d === e
e === f
e === f
f === g
d === e
e === e
f === e
f === f
Array
(
)
*/
```
