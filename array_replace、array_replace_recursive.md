```php
array_replace ( array $array1 [, array $... ] ) : array

array_replace_recursive ( array $array1 [, array $... ] ) : array
```

1. 当数组之间中有相同的键名，后面的值覆盖前面的值。
2. 后面的键，第一个数组中不存在，则将这个元素放到第一个数组中。

```php
<?php
$base = ["orange", "banana", "apple", "raspberry"];
$replacements = [0 => "pineapple", 4 => "cherry"];
$replacements2 = [0 => "grape"];

$basket = array_replace($base, $replacements, $replacements2);
print_r($basket);

/*
Array
(
    [0] => grape
    [1] => banana
    [2] => apple
    [3] => raspberry
    [4] => cherry
)
*/
```

```php
<?php
$base = [&#039;citrus&#039; => ["orange"], &#039;berries&#039; => ["blackberry", "raspberry"], &#039;others&#039; => &#039;banana&#039;];
$replacements = [&#039;citrus&#039; => &#039;pineapple&#039;, &#039;berries&#039; => [&#039;blueberry&#039;], &#039;others&#039; => [&#039;litchis&#039;]];
$replacements2 = [&#039;citrus&#039; => [&#039;pineapple&#039;], &#039;berries&#039; => [&#039;blueberry&#039;], &#039;others&#039; => &#039;litchis&#039;];

$basket = array_replace_recursive($base, $replacements, $replacements2);
print_r($basket);

/*
Array
(
    [citrus] => Array
        (
            [0] => pineapple
        )

    [berries] => Array
        (
            [0] => blueberry
            [1] => raspberry
        )

    [others] => litchis
)
*/
```