```php
array_search ( mixed $needle , array $haystack [, bool $strict = FALSE ] ) : mixed
```

1. needle 中文翻译是针，haystack 中文翻译是草。草里寻针。
2. 第一个参数是字符串的话，就是保证大小写也要一致才算匹配成功。
3. 第三个参数是 true 代表全等才算匹配成功，默认是 false，表示只要相等，不管类型是否一样就是匹配成功。

```php
<?php
$array = [0 => &#039;blue&#039;, 1 => &#039;red&#039;, 2 => &#039;green&#039;, 3 => &#039;red&#039;];

$key1 = array_search(&#039;green&#039;, $array);
$key2 = array_search(&#039;red&#039;, $array);

var_dump($key1);
var_dump($key2);

/*
int(2)
int(1)
*/
```