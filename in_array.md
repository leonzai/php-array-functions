```php
in_array ( mixed $needle , array $haystack [, bool $strict = FALSE ] ) : bool
```

1. needle 中文翻译是针，haystack 中文翻译是草。草里寻针。
2. 第一个参数是字符串的话，就是保证大小写也要一致才算匹配成功。
3. 第三个参数是 true 代表全等才算匹配成功，默认是 false，表示只要相等，不管类型是否一样就是匹配成功。

```php
<?php
$a = [['p', 'h'], ['p', 'r'], 'o'];

if (in_array(['p', 'h'], $a)) {
    echo "'ph' was found\n";
}

if (in_array(['f', 'i'], $a)) {
    echo "'fi' was found\n";
}

if (in_array('o', $a)) {
    echo "'o' was found\n";
}

/*
'ph' was found
'o' was found
*/
```