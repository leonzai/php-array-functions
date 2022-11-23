```php
uksort ( array &$array , callable $key_compare_func ) : bool
```

```php
<?php
function cmp($a, $b)
{
    return strcasecmp($a, $b);
}

$a = ["John" => 1, "Earth" => 2, "apple" => 3, "banana" => 4];

uksort($a, "cmp");

foreach ($a as $key => $value) {
    echo "$key: $value\n";
}

/*
apple: 3
banana: 4
Earth: 2
John: 1

*/
```