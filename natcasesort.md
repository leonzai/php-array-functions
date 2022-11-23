```php
natcasesort ( array &$array ) : bool

// natcasesort($array) 等价于 sort($array, SORT_NATURAL | SORT_FLAG_CASE)
```

```php
<?php
$array1 = $array2 = ['IMG0.png', 'img12.png', 'img10.png', 'img2.png', 'img1.png', 'IMG3.png'];

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
