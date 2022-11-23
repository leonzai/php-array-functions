```php
array_slice ( array $array , int $offset [, int $length = NULL [, bool $preserve_keys = FALSE ]] ) : array
```

1. 参数 $array 是要处理的数组。
2. 参数 $offset 表示数组的起始位置，如果是非负数，表示从数组第 $offset 个元素后面开始计数，如果是负数，表示从数组倒数第 $offset 个元素后面开始计数。$offset 超出数组长度，则返回空数组。
3. 参数 $length 是正数，表示取出几个元素，如果超出数组长度，则有多少取出多少。如果是负数，表示取到数组倒数第 $length 个。如果未提供该参数，就是往后一直取，取完数组。
4. 参数 $preserve_keys 保留数字索引，默认不保留。无论参数值是什么，字符串索引始终保留。

```php
&lt;?php
$input = [&quot;a&quot;, &quot;b&quot;, &quot;c&quot;, &quot;d&quot;, &quot;e&quot;];

$output = array_slice($input, 2);      //  &quot;c&quot;, &quot;d&quot;, and &quot;e&quot;
$output = array_slice($input, -2, 1);  //  &quot;d&quot;
$output = array_slice($input, 0, 3);   //  &quot;a&quot;, &quot;b&quot;, and &quot;c&quot;

print_r(array_slice($input, 2, -1));
print_r(array_slice($input, 2, -1, true));

/*
Array
(
    [0] =&gt; c
    [1] =&gt; d
)
Array
(
    [2] =&gt; c
    [3] =&gt; d
)
*/
```