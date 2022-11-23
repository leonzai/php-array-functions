```php
shuffle ( array &$array ) : bool
```

```php
<?php
$array = [
    "a" => 3,
    "a1" => 2,
    "a2" => 1,
    "a3" => 4,
    "a4" => 5,
    "a5" => 12,
];

shuffle($array);
print_r($array);

/*
Array
(
    [0] => 2
    [1] => 5
    [2] => 3
    [3] => 12
    [4] => 4
    [5] => 1
)
*/
```