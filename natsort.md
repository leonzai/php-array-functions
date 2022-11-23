```php
natsort ( array &amp;$array ) : bool
	
// natsort($array) 等价于 sort($array, SORT_NATURAL)
```

```php
&lt;?php
$array1 = $array2 = [&quot;img12.png&quot;, &quot;img10.png&quot;, &quot;img2.png&quot;, &quot;img1.png&quot;];

natsort($array2);
print_r($array2);

/*
Array
(
    [3] =&gt; img1.png
    [2] =&gt; img2.png
    [1] =&gt; img10.png
    [0] =&gt; img12.png
)
*/
```
