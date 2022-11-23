```php
array_fill ( int $start_index , int $num , mixed $value ) : array
```

```php
<?php
$a = array_fill(5, 6, 'banana');
$b = array_fill(-2, 4, 'pear');
print_r($a);
print_r($b);

/*
Array
(
    [5] => banana
    [6] => banana
    [7] => banana
    [8] => banana
    [9] => banana
    [10] => banana
)
Array
(
    [-2] => pear
    [0] => pear
    [1] => pear
    [2] => pear
)
*/
```