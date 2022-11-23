```php
array_reduce ( array $array , callable $callback [, mixed $initial = NULL ] ) : mixed
```

1. 将数组各个元素依次传递给闭包函数，最后汇总返回一个值。
2. 回调函数 $callback 第一个参数是上一次迭代的返回值，如果此次是第一次迭代，那么这个值是函数的第三个参数 $initial。
3. 如果是空数组，将直接返回 $initial。

```php
<?php
$a = [
    [&#039;id&#039; => 1, &#039;name&#039; => &#039;leon&#039;,],
    [&#039;id&#039; => 2, &#039;name&#039; => &#039;千金&#039;,],
    [&#039;id&#039; => 3, &#039;name&#039; => &#039;一刻&#039;,],
];

var_dump("请输出 leon,千金,一刻");

// foreach 方式
$res = &#039;&#039;;
foreach ($a as $arr) {
    $res .= &#039;,&#039; . $arr[&#039;name&#039;];
}

var_dump(trim($res, &#039;,&#039;));

// array_reduce 方式
$string = array_reduce($a, function ($v1, $v2) {
    return $v1 . &#039;,&#039; . $v2[&#039;name&#039;];
});

var_dump(trim($string, &#039;,&#039;));
```