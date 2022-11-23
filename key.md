```php
key ( array $array ) : mixed
```

1. 如果数组是空数组或者指针超出了数组的长度，函数返回 NULL。

```php
<?php
$array = [
    'fruit1' => 'apple',
    'fruit2' => 'orange',
    'fruit3' => 'grape',
    'fruit4' => 'apple',
    'fruit5' => 'apple'
];

while ($fruit_name = current($array)) {
    if ($fruit_name == 'apple') {
        echo key($array) . "\n";
    }
    next($array);
}

/*
fruit1
fruit4
fruit5
*/
```