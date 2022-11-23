```php
array_key_exists ( mixed $key , array $array ) : bool
```

1. 只会判断最外面一层数组，不会递归判断。
2. 与 isset 区别：如果元素的值是 null，isset 返回 false，key_exists 返回 true。

```php
<?php
$arr = [
    &#039;first&#039; => 1,
    &#039;second&#039; => null
];

var_dump(array_key_exists(&#039;first&#039;, $arr));
var_dump(array_key_exists(&#039;second&#039;, $arr));
var_dump(isset($arr[&#039;second&#039;]));

/*
bool(true)
bool(true)
bool(false)
*/
```