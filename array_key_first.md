```php
array_key_first ( array $array ) : mixed

// 注意：php 7.3 才有的函数
// 返回数组第一个键名，空数组返回 null。
```

```php
<?php
$array = ['a' => 1, 'b' => 2, 'c' => 3];

$firstKey = array_key_first($array);

var_dump($firstKey);

/*
string(1) "a"
*/
```

**如果是老版 php，请用下面函数代替**

```php
if (!function_exists('array_key_first')) {
    function array_key_first(array $arr) {
        foreach($arr as $key => $unused) {
            return $key;
        }
        return NULL;
    }
}
```