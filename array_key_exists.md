```php
array_key_exists ( mixed $key , array $array ) : bool
```

1. 只会判断最外面一层数组，不会递归判断。
2. 与 isset 区别：如果元素的值是 null，isset 返回 false，key_exists 返回 true。

```php
<?php
$arr = [
    'first' => 1,
    'second' => null
];

var_dump(array_key_exists('first', $arr));
var_dump(array_key_exists('second', $arr));
var_dump(isset($arr['second']));

/*
bool(true)
bool(true)
bool(false)
*/
```