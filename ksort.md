```php
ksort ( array &$array [, int $sort_flags = SORT_REGULAR ] ) : bool
```
与 `sort` 函数的**唯一区别**是：ksort 使用键名排序，返回数组保留键名，而 sort 排序的是数组元素的值，返回数组不再保留键名。

**第二个参数效果完全等同于 sort，请参考**

[https://qianjinyike.com/【sort】排序数组（不再保留键名）](https://qianjinyike.com/【sort】排序数组（不再保留键名） "https://qianjinyike.com/【sort】排序数组（不再保留键名）")

```php
<?php
$fruits = [
    "d" => "lemon",
    "a" => "orange",
    "b" => "banana",
    "c" => "apple",
];
ksort($fruits);

foreach ($fruits as $key => $val) {
    echo "$key = $val\n";
}

/*
a = orange
b = banana
c = apple
d = lemon
*/
```