```php
array_splice ( array &$input , int $offset [, int $length = count($input) [, mixed $replacement = array() ]] ) : array
```

1. 参数 $input 是要处理的数组， $offset 和 $length 表达了要移除的部分，$replacement 是要替换移除部分的内容。该参数的数字键不被保留。
2. 参数 $offset 表示数组的起始位置，如果是是非负数，表示从数组第 $offset 个元素后面开始计数，如果是负数，表示从数组倒数第 $offset 个元素后面开始计数。$offset 超出数组长度，则返回空数组。
3. 参数 $length 是正数，表示取出几个元素，如果超出数组长度，则有多少取出多少。如果是负数，表示取到数组倒数第 $length 个。如果未提供改参数，就是往后一直取，取完数组。
4. 参数 $replacement 中的键不会保留，如果该参数不是数组，会强制转化成数组，如果是一个对象或者是 null，最终的行为不可预测。

```php
<?php
$input = array("red", "green", "blue", "yellow");
array_splice($input, 2);
var_dump($input);

$input = array("red", "green", "blue", "yellow");
array_splice($input, 1, -1);
var_dump($input);

$input = array("red", "green", "blue", "yellow");
array_splice($input, 1, count($input), "orange");
var_dump($input);

$input = array("red", "green", "blue", "yellow");
array_splice($input, -1, 1, array("black", "maroon"));
var_dump($input);

/*
array(2) {
  [0]=>
  string(3) "red"
  [1]=>
  string(5) "green"
}
array(2) {
  [0]=>
  string(3) "red"
  [1]=>
  string(6) "yellow"
}
array(2) {
  [0]=>
  string(3) "red"
  [1]=>
  string(6) "orange"
}
array(5) {
  [0]=>
  string(3) "red"
  [1]=>
  string(5) "green"
  [2]=>
  string(4) "blue"
  [3]=>
  string(5) "black"
  [4]=>
  string(6) "maroon"
}
*/
```

等价函数

```php
array_push($input, $x, $y);
array_splice($input, count($input), 0, array($x, $y));

array_pop($input);
array_splice($input, -1);

array_shift($input);
array_splice($input, 0, 1);

array_unshift($input, $x, $y);
array_splice($input, 0, 0, array($x, $y));

$input[$x] = $y; 
array_splice($input, $x, 1, $y);
```