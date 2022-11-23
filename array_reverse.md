```php
array_reverse ( array $array [, bool $preserve_keys = FALSE ] ) : array
```

1. 第二个参数表示是否保留数字索引。字符串索引不会受该参数影响，始终保留。

```php
&lt;?php
$input  = array(&quot;php&quot;, 4.0, array(&quot;green&quot;, &quot;red&quot;));
$reversed = array_reverse($input);
$preserved = array_reverse($input, true);

print_r($reversed);
print_r($preserved);

/*
Array
(
    [0] =&gt; Array
        (
            [0] =&gt; green
            [1] =&gt; red
        )

    [1] =&gt; 4
    [2] =&gt; php
)
Array
(
    [2] =&gt; Array
        (
            [0] =&gt; green
            [1] =&gt; red
        )

    [1] =&gt; 4
    [0] =&gt; php
)
*/
```