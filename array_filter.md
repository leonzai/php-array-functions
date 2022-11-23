```php
array_filter ( array $array [, callable $callback [, int $flag = 0 ]] ) : array
```
1. 一次将每个元素传递给回调函数 $callback，函数返回 true，则当前元素会被放到返回的数组中。
2. $flag 默认是 0，表示把元素的值传递给回调函数。ARRAY_FILTER_USE_KEY 表示只传递键名，ARRAY_FILTER_USE_BOTH 将键值对都传递给回调函数。
3. 不要在回调函数中改变数组。

```php
&lt;?php

$entry = [
    0 =&gt; &#039;foo&#039;,
    1 =&gt; false,
    2 =&gt; -1,
    3 =&gt; null,
    4 =&gt; &#039;&#039;,
    5 =&gt; &#039;0&#039;,
    6 =&gt; 0,
];

print_r(array_filter($entry));

/*
Array
(
    [0] =&gt; foo
    [2] =&gt; -1
)
*/
```

```php
&lt;?php

$arr = [&#039;a&#039; =&gt; 1, &#039;b&#039; =&gt; 2, &#039;c&#039; =&gt; 3, &#039;d&#039; =&gt; 4];

var_dump(array_filter($arr, function ($k) {
    return $k == &#039;b&#039;;
}, ARRAY_FILTER_USE_KEY));

var_dump(array_filter($arr, function ($v, $k) {
    return $k == &#039;b&#039; || $v == 4;
}, ARRAY_FILTER_USE_BOTH));

/*
array(1) {
  [&quot;b&quot;]=&gt;
  int(2)
}
array(2) {
  [&quot;b&quot;]=&gt;
  int(2)
  [&quot;d&quot;]=&gt;
  int(4)
}
*/
```

```php
&lt;?php
function odd($var)
{
    return $var &amp; 1;
}

function even($var)
{
    return !($var &amp; 1);
}

$array1 = [&#039;a&#039; =&gt; 1, &#039;b&#039; =&gt; 2, &#039;c&#039; =&gt; 3, &#039;d&#039; =&gt; 4, &#039;e&#039; =&gt; 5];
$array2 = [6, 7, 8, 9, 10, 11, 12];

print_r(array_filter($array1, &quot;odd&quot;));

print_r(array_filter($array2, &quot;even&quot;));

/*
Array
(
    [a] =&gt; 1
    [c] =&gt; 3
    [e] =&gt; 5
)
Array
(
    [0] =&gt; 6
    [2] =&gt; 8
    [4] =&gt; 10
    [6] =&gt; 12
)
*/
```