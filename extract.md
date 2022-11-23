```php
extract ( array &$array [, int $flags = EXTR_OVERWRITE [, string $prefix = NULL ]] ) : int
```

| 第二个参数 $flags（用来处理非法的键名、数字键名、冲突键名） | 效果                                                         |
| ----------------------------------------------------------- | ------------------------------------------------------------ |
| **`EXTR_OVERWRITE`**（默认值）                              | 解析出来的变量和已存在变量有冲突，覆盖已存在的变量           |
| **`EXTR_SKIP`**                                             | 解析出来的变量和已存在变量有冲突，不覆盖已存在的变量         |
| **`EXTR_PREFIX_SAME`**                                      | 解析出来的变量和已存在变量有冲突，把第三个参数加在解析出来的变量前作为前缀 |
| **`EXTR_PREFIX_ALL`**                                       | 第三个参数加在所有解析出来的变量前作为前缀                   |
| **`EXTR_PREFIX_INVALID`**                                   | 如果键名是数字或者非法键名，则第三个参数加在这些解析出来的变量前作为前缀 |
| **`EXTR_IF_EXISTS`**                                        | 解析出来的变量和已存在变量有冲突，覆盖已存在的变量，其他都不做处理。 |
| **`EXTR_PREFIX_IF_EXISTS`**                                 | 解析出来的变量和已存在变量有冲突，把第三个参数加在解析出来的变量前作为前缀，其他都不做处理。 |
| **`EXTR_REFS`**                                             | 以引用的方式把变量解析出来，可以单独使用此参数值，也可以和其他的参数值使用或运算结合使用 |

1. 函数不要使用在不可信的数组上面，比如： `$_GET`, `$_FILES`。
2. 数字索引数组不会产生任何结果，除非搭配了 EXTR_PREFIX_ALL 或 EXTR_PREFIX_INVALID。
3. 第二个参数用来处理非法的键名、数字键名、冲突键名。
4. 第三个参数可选。请注意 prefix 仅在第二个参数的值是 EXTR_PREFIX_SAME，EXTR_PREFIX_ALL，EXTR_PREFIX_INVALID 或 EXTR_PREFIX_IF_EXISTS 时需要。如果附加了前缀后的结果不是合法的变量名，将直接跳过。前缀和数组键名之间会自动加上一个下划线。

```php
<?php
$size = "large";

$var_array = [
    "color" => "blue",
    "size"  => "medium",
    "shape" => "sphere"
];

extract($var_array, EXTR_PREFIX_SAME, "a");

echo "$color, $size, $shape, $a_size\n";

/*
blue, large, sphere, medium
*/
```