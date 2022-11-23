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

$array = [&#039;a&#039; => 4, &#039;b&#039; => 8, &#039;c&#039; => -1, &#039;d&#039; => -9,];
uasort($array, &#039;cmp&#039;);

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