```php
natcasesort ( array &$array ) : bool

// natcasesort($array) 等价于 sort($array, SORT_NATURAL | SORT_FLAG_CASE)
```

```php
<?php
$array1 = $array2 = [&#039;IMG0.png&#039;, &#039;img12.png&#039;, &#039;img10.png&#039;, &#039;img2.png&#039;, &#039;img1.png&#039;, &#039;IMG3.png&#039;];

natcasesort($array2);
print_r($array2);

/*
Array
(
    [0] => IMG0.png
    [4] => img1.png
    [3] => img2.png
    [5] => IMG3.png
    [2] => img10.png
    [1] => img12.png
)
*/
```
