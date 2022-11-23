```php
compact ( mixed $varname1 [, mixed $... ] ) : array
```

1. 7.3 之前变量不存在会跳过，之后会爆出 E_NOTICE。
2. 参数可以是个数组，该函数会递归地检测变量生成数组。
3. 参数不可以是超全局数组，诸如 `$_GET` 之类。

```php
<?php
$city  = "San Francisco";
$state = "CA";
$event = "SIGGRAPH";

$location_vars = array("city", "state");

$result = compact("event", $location_vars);
print_r($result);

/*
Array
(
    [event] => SIGGRAPH
    [city] => San Francisco
    [state] => CA
)
*/
```