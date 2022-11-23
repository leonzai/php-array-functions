```php
array_reverse ( array $array [, bool $preserve_keys = FALSE ] ) : array
```

1. 第二个参数表示是否保留数字索引。字符串索引不会受该参数影响，始终保留。

```php
<?php
$input  = array("php", 4.0, array("green", "red"));
$reversed = array_reverse($input);
$preserved = array_reverse($input, true);

print_r($reversed);
print_r($preserved);

/*
Array
(
    [0] => Array
        (
            [0] => green
            [1] => red
        )

    [1] => 4
    [2] => php
)
Array
(
    [2] => Array
        (
            [0] => green
            [1] => red
        )

    [1] => 4
    [0] => php
)
*/
```