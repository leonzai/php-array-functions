```php
array_reduce ( array $array , callable $callback [, mixed $initial = NULL ] ) : mixed
```

1. 将数组各个元素依次传递给闭包函数，最后汇总返回一个值。
2. 回调函数 $callback 第一个参数是上一次迭代的返回值，如果此次是第一次迭代，那么这个值是函数的第三个参数 $initial。
3. 如果是空数组，将直接返回 $initial。

```php
<?php
$a = [
    ['id' => 1, 'name' => 'leon',],
    ['id' => 2, 'name' => '千金',],
    ['id' => 3, 'name' => '一刻',],
];

var_dump("请输出 leon,千金,一刻");

// foreach 方式
$res = '';
foreach ($a as $arr) {
    $res .= ',' . $arr['name'];
}

var_dump(trim($res, ','));

// array_reduce 方式
$string = array_reduce($a, function ($v1, $v2) {
    return $v1 . ',' . $v2['name'];
});

var_dump(trim($string, ','));
```