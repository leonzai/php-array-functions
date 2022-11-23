```php
array_replace ( array $array1 [, array $... ] ) : array

array_replace_recursive ( array $array1 [, array $... ] ) : array
```

1. 当数组之间中有相同的键名，后面的值覆盖前面的值。
2. 后面的键，第一个数组中不存在，则将这个元素放到第一个数组中。

```php
&lt;?php
$base = [&quot;orange&quot;, &quot;banana&quot;, &quot;apple&quot;, &quot;raspberry&quot;];
$replacements = [0 =&gt; &quot;pineapple&quot;, 4 =&gt; &quot;cherry&quot;];
$replacements2 = [0 =&gt; &quot;grape&quot;];

$basket = array_replace($base, $replacements, $replacements2);
print_r($basket);

/*
Array
(
    [0] =&gt; grape
    [1] =&gt; banana
    [2] =&gt; apple
    [3] =&gt; raspberry
    [4] =&gt; cherry
)
*/
```

```php
&lt;?php
$base = [&#039;citrus&#039; =&gt; [&quot;orange&quot;], &#039;berries&#039; =&gt; [&quot;blackberry&quot;, &quot;raspberry&quot;], &#039;others&#039; =&gt; &#039;banana&#039;];
$replacements = [&#039;citrus&#039; =&gt; &#039;pineapple&#039;, &#039;berries&#039; =&gt; [&#039;blueberry&#039;], &#039;others&#039; =&gt; [&#039;litchis&#039;]];
$replacements2 = [&#039;citrus&#039; =&gt; [&#039;pineapple&#039;], &#039;berries&#039; =&gt; [&#039;blueberry&#039;], &#039;others&#039; =&gt; &#039;litchis&#039;];

$basket = array_replace_recursive($base, $replacements, $replacements2);
print_r($basket);

/*
Array
(
    [citrus] =&gt; Array
        (
            [0] =&gt; pineapple
        )

    [berries] =&gt; Array
        (
            [0] =&gt; blueberry
            [1] =&gt; raspberry
        )

    [others] =&gt; litchis
)
*/
```