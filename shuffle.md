```php
shuffle ( array &amp;$array ) : bool
```

```php
&lt;?php
$array = [
    &quot;a&quot; =&gt; 3,
    &quot;a1&quot; =&gt; 2,
    &quot;a2&quot; =&gt; 1,
    &quot;a3&quot; =&gt; 4,
    &quot;a4&quot; =&gt; 5,
    &quot;a5&quot; =&gt; 12,
];

shuffle($array);
print_r($array);

/*
Array
(
    [0] =&gt; 2
    [1] =&gt; 5
    [2] =&gt; 3
    [3] =&gt; 12
    [4] =&gt; 4
    [5] =&gt; 1
)
*/
```