```php
array_map ( callable $callback , array $array1 [, array $... ] ) : array
```

| 第一个参数 | 其他参数 | array_map 返回值                                             |
| ---------- | -------- | ------------------------------------------------------------ |
| null       | 一个数组 | 直接返回这个数组                                             |
| null       | 多个数组 | 将每个数组转化成索引数组，然后将他们索引相同的值组成新的数组（看例子） |
| 回调函数   | 一个数组 | 将数组的每个值都依次传到回调函数中，将回调函数返回值组成新的数组作为 array_map 的返回值，保留键名 |
| 回调函数   | 多个数组 | 将每个数组转化成索引数组，再将多个数组的每个值都依次传到回调函数中，将回调函数返回值组成新的数组作为 array_map 的返回值 |

```php
<?php
$a = [
    [&#039;id&#039; => 1, &#039;name&#039; => &#039;千金&#039;],
    [&#039;id&#039; => 2, &#039;name&#039; => null],
    [&#039;id&#039; => 3, &#039;name&#039; => &#039;一刻&#039;],
];

$res1 = [];
foreach ($a as $arr) {
    if (!$arr[&#039;name&#039;]) {
        $arr[&#039;name&#039;] = &#039;匿名&#039;;
    }
    $res1[] = $arr;
}

$res2 = array_map(function ($value) {
    if (!$value[&#039;name&#039;]) {
        $value[&#039;name&#039;] = &#039;匿名&#039;;
    }
    return $value;
}, $a);

var_dump($res1 == $res2);

/*
bool(true)
*/
```

```php
<?php
$arr = [&#039;stringkey&#039; => &#039;value&#039;];
var_dump(array_map(null,  $arr));

/*
array(1) {
  ["stringkey"]=>
  string(5) "value"
}
*/

$a = [1, 2, 3,];
$b = [&#039;one&#039;, &#039;two&#039;, &#039;three&#039;, ];
$c = [&#039;uno&#039;, &#039;dos&#039;, ];

$d = array_map(null, $a, $b, $c);
print_r($d);

/*
Array
(
    [0] => Array
        (
            [0] => 1
            [1] => one
            [2] => uno
        )

    [1] => Array
        (
            [0] => 2
            [1] => two
            [2] => dos
        )

    [2] => Array
        (
            [0] => 3
            [1] => three
            [2] =>
        )

)
*/

function triple($n)
{
    return $n * 3;
}

$a = [1, 2, 3, "xx" => 4, 5];
$b = array_map(&#039;triple&#039;, $a);
print_r($b);

/*
Array
(
    [0] => 3
    [1] => 6
    [2] => 9
    [xx] => 12
    [4] => 15
)
*/

function a($n, $m)
{
    return "{$n} and {$m}";
}

function b($n, $m)
{
    return [$n => $m];
}

$a = [1, "test" => 2,];
$b = [&#039;aa&#039;, &#039;bb&#039;,];

$c = array_map(&#039;a&#039;, $a, $b);
print_r($c);

$d = array_map(&#039;b&#039;, $a, $b);
print_r($d);

/*
Array
(
    [0] => 1 and aa
    [1] => 2 and bb
)
Array
(
    [0] => Array
        (
            [1] => aa
        )

    [1] => Array
        (
            [2] => bb
        )

)
*/

// 应用
$integers = array_map (&#039;intval&#039;, $integers);
$safeStrings = array_map (&#039;mysql_real_escape_string&#039;, $unsafeStrings);
```
