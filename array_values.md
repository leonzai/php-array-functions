```php
array_values ( array $array ) : array
```

1. 返回包含所有值的数组，所有键变成数字索引，不会保留原有键。

```php
&lt;?php
$array = [&quot;size&quot; =&gt; &quot;XL&quot;, [&quot;color&quot; =&gt; &quot;gold&quot;]];
print_r(array_values($array));

/*
Array
(
    [0] =&gt; XL
    [1] =&gt; Array
        (
            [color] =&gt; gold
        )

)
*/
```