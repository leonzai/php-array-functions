```php
array_merge ([ array $... ] ) : array
	
array_merge_recursive ([ array $... ] ) : array
```

1. php 7.4 可以不传任何参数，返回空数组，否则传递的参数必须是一个数组，或者多个数组。
2. 传一个数组，则这个数组将最为最终返回值。
3. 传递多个数组，则合并数组，如果键名一样且是字符串，则后来的值覆盖前面的值，如果键名一样且是数字，不会覆盖。
4. 数字索引的数组在合并时候会被重新索引，从 0 开始，不会保留之前的索引。

```php
<?php
$array1 = array("color" => "red", 2 => 2, 4);
$array2 = array("a", "b", "color" => "green", "shape" => "trapezoid", 2 => 4);
$result = array_merge($array1, $array2);
print_r($result);

/*
Array
(
    [color] => green
    [0] => 2
    [1] => 4
    [2] => a
    [3] => b
    [shape] => trapezoid
    [4] => 4
)
*/
```

# 请注意，当使用 array_merge_recursive 时候，相同的键名不会覆盖，而是并存。

```php
<?php
$ar1 = array("color" => array("favorite" => "red"), 5);
$ar2 = array(10, "color" => array("favorite" => "green", "blue"));
$result = array_merge_recursive($ar1, $ar2);
print_r($result);

/**
Array
(
    [color] => Array
        (
            [favorite] => Array
                (
                    [0] => red
                    [1] => green
                )

            [0] => blue
        )

    [0] => 5
    [1] => 10
)
*/
```