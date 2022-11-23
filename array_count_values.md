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
    [&#039;id&#039; => 1, &#039;userId&#039; => 5],
    [&#039;id&#039; => 2, &#039;userId&#039; => 5],
    [&#039;id&#039; => 3, &#039;userId&#039; => 6],
];

echo array_count_values(array_column($list, &#039;userId&#039;))[5];

/*
2
*/
```