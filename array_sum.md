```php
array_sum ( array $array ) : number
```

1. 空数组返回 0。

```php
<?php
$a = [2, 4, 6, 8];
echo "数组 a 求和：" . array_sum($a) . "\n";

$b = ["a" => 1.2, "b" => 2.3, "c" => 3.4];
echo "数组 b 求和：" . array_sum($b) . "\n";

echo "数组 a 求平均数：" . array_sum($a) / count($a);

/*
数组 a 求和：20
数组 b 求和：6.9
数组 a 求平均数：5
*/
```