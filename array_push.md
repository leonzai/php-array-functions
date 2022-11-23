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
int(4)
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

$fruit = array_push($stack, 123);
var_dump($stack);

/*
array(5) {
  [0]=>
  string(1) "a"
  [1]=>
  string(1) "b"
  [2]=>
  string(1) "c"
  [3]=>
  string(1) "d"
  [4]=>
  int(123)
}
*/

$fruit = array_push($stack, 456, 789);
var_dump($stack);

/*
array(7) {
  [0]=>
  string(1) "a"
  [1]=>
  string(1) "b"
  [2]=>
  string(1) "c"
  [3]=>
  string(1) "d"
  [4]=>
  int(123)
  [5]=>
  int(456)
  [6]=>
  int(789)
}
*/
```