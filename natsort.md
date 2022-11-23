```php
natsort ( array &$array ) : bool
	
// natsort($array) 等价于 sort($array, SORT_NATURAL)
```

```php
<?php
$array1 = $array2 = ["img12.png", "img10.png", "img2.png", "img1.png"];

natsort($array2);
print_r($array2);

/*
Array
(
    [3] => img1.png
    [2] => img2.png
    [1] => img10.png
    [0] => img12.png
)
*/
```
