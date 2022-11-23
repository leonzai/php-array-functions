```php
array_count_values( array $array) : array
```

```php
<?php

$array = array(1, "hello", 1, "world", "hello");
$result = array_count_values($array);
var_dump($result);

/*
array(3) {
  [1]=>
  int(2)
  ["hello"]=>
  int(2)
  ["world"]=>
  int(1)
}
*/

# 计算某个键值对出现的次数
$list = [
    ['id' => 1, 'userId' => 5],
    ['id' => 2, 'userId' => 5],
    ['id' => 3, 'userId' => 6],
];

echo array_count_values(array_column($list, 'userId'))[5];

/*
2
*/
```