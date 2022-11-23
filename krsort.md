```php
krsort ( array &$array [, int $sort_flags = SORT_REGULAR ] ) : bool
```
与 `ksort` 函数的**唯一区别**是：排序的方向不同。

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
krsort($fruits);

foreach ($fruits as $key => $val) {
    echo "$key = $val\n";
}

/*
d = lemon
c = apple
b = banana
a = orange
*/
```