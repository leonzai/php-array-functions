```php
array_push ( array &$array [, mixed $... ] ) : int
```

1. 该函数返回追加后数组的长度。
2. 7.3 开始可以只传递一个参数，只有一个参数时，对数组不作任何改变，返回数组长度。
3. 如果只有两个参数，效果等同于 `$array[]='append';` 此时尽量使用后者。

```php
<?php
$stack = ["a", "b", "c", "d"];
$fruit = array_push($stack);
var_dump($fruit);
var_dump($stack);

/*
int(4)         之所以是 4 ，是因为根本就没有 push 东西进去
array(4) {
  [0]=>
  string(1) "a"
  [1]=>
  string(1) "b"
  [2]=>
  string(1) "c"
  [3]=>
  string(1) "d"
}
*/
```
