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
$base = ['citrus' => ["orange"], 'berries' => ["blackberry", "raspberry"], 'others' => 'banana'];
$replacements = ['citrus' => 'pineapple', 'berries' => ['blueberry'], 'others' => ['litchis']];
$replacements2 = ['citrus' => ['pineapple'], 'berries' => ['blueberry'], 'others' => 'litchis'];

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