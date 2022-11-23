```php
array_keys ( array $array ) : array

array_keys ( array $array , mixed $search_value [, bool $strict = FALSE ] ) : array


// $array：需要处理的数组
// $search_value：数组中值等于 $search_value 的键名都返回出来
// $preserve_keys：默认是 false，如果是 true，在比较 $search_value 时采用全等
```

```php
&lt;?php
$array = [&quot;blue&quot;, &quot;red&quot;, 1, &quot;1&quot;, &quot;blue&quot;];
print_r(array_keys($array, &quot;1&quot;, true));

$array = [&quot;blue&quot;, &quot;red&quot;, [&quot;green&quot;], &quot;blue&quot;, &quot;blue&quot;];
print_r(array_keys($array, [&#039;green&#039;]));

/*
Array
(
    [0] =&gt; 3
)
Array
(
    [0] =&gt; 2
)
*/
```
