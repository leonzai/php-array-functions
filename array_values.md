```php
array_values ( array $array ) : array
```

1. 返回包含所有值的数组，所有键变成数字索引，不会保留原有键。

```php
<?php
$array = ["size" => "XL", ["color" => "gold"]];
print_r(array_values($array));

/*
Array
(
    [0] => XL
    [1] => Array
        (
            [color] => gold
        )
)
*/
```
