```php
array_intersect_ukey ( array $array1 , array $array2 [, array $... ], callable $key_compare_func ) : array
```

1. 首先内部对数据进行排序，目的是提高比较效率
2. 第一个数组的元素和第二个数组元素集合依次比较
3. 比较的是键，使用自定义函数进行比较，如果相等则这个元素被放置到返回数组中，否则继续比较。
4. 比较的时候如果键相等，就开始下次循环比较，并且从第一个数组中下一个元素开始比较。

```php
<?php
function key_compare_func($key1, $key2)
{
    echo(str_pad($key1, 10) . ' - ' . $key2 . "\n");

    if ($key1 == $key2){
        return 0;
    }

    if ($key1 > $key2){
        return 1;
    }

    return -1;
}

$array1 = array('blue' => 1, 'red' => 2, 'green' => 3, 'purple' => 4);
$array2 = array('green' => 5, 'blue' => 6, 'yellow' => 7, 'cyan' => 8);

var_dump(array_intersect_ukey($array1, $array2, 'key_compare_func'));
/*
blue       - red
red        - green
blue       - green
red        - purple
green      - purple
green      - blue
yellow     - blue
green      - yellow
yellow     - cyan
green      - cyan
blue       - cyan
blue       - blue
green      - cyan
green      - green
purple     - yellow
red        - yellow
array(2) {
  ["blue"]=>
  int(1)
  ["green"]=>
  int(3)
}
*/
```
