```php
array_pop ( array &$array ) : mixed
```

1. 空数组返回 NULL。
2. 函数运行完，数组内部指针将返回到数组头部。

```php
<?php
$stack = ["a", "b", "c", "d"];
$fruit = array_pop($stack);
var_dump($fruit);
var_dump($stack);

/*
string(1) "d"
array(3) {
  [0]=>
  string(1) "a"
  [1]=>
  string(1) "b"
  [2]=>
  string(1) "c"
}
*/
```