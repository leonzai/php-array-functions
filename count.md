```php
count ( mixed $array_or_countable [, int $mode = COUNT_NORMAL ] ) : int
```

1. 第二个参数默认值 COUNT_NORMAL，表示计算最外面一层数组的长度。还可以是 COUNT_RECURSIVE，将会递归计算数组的长度。

```php
<?php
$food = array('fruits' => array('orange', 'banana', 'apple'),
    'veggie' => array('carrot', 'collard', 'pea'));

echo count($food, COUNT_RECURSIVE); // output 8

echo count($food); // output 2
```