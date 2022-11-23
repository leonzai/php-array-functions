```php
natcasesort ( array &amp;$array ) : bool

// natcasesort($array) 等价于 sort($array, SORT_NATURAL | SORT_FLAG_CASE)
```

```php
&lt;?php
$array1 = $array2 = [&#039;IMG0.png&#039;, &#039;img12.png&#039;, &#039;img10.png&#039;, &#039;img2.png&#039;, &#039;img1.png&#039;, &#039;IMG3.png&#039;];

natcasesort($array2);
print_r($array2);

/*
Array
(
    [0] =&gt; IMG0.png
    [4] =&gt; img1.png
    [3] =&gt; img2.png
    [5] =&gt; IMG3.png
    [2] =&gt; img10.png
    [1] =&gt; img12.png
)
*/
```
