```php
uasort ( array &$array , callable $value_compare_func ) : bool
```

```php
<?php
function cmp($a, $b)
{
    if ($a == $b) {
        return 0;
    }
    return ($a < $b) ? -1 : 1;
}

$array = ['a' => 4, 'b' => 8, 'c' => -1, 'd' => -9,];
uasort($array, 'cmp');

print_r($array);

/*
Array
(
    [d] => -9
    [c] => -1
    [a] => 4
    [b] => 8
)
*/
```