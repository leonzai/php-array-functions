```php
array_multisort ( array &$array1 [, mixed $array1_sort_order = SORT_ASC [, mixed $array1_sort_flags = SORT_REGULAR [, mixed $... ]]] ) : bool
    
// 字符串索引将被保留，数字索引会被重新索引。
// $array1 被排序的数组
// $array1_sort_order 指定排序的方向，默认是升序 SORT_ASC，还可以是降序 SORT_DESC。
// $array1_sort_flags 参数等同于 sort 的第二个参数，详情参考 sort 第二个参数。
    
// 这个函数定义的不是很好，具体我们看下面的例子。
```

```php
<?php
$ar1 = [10, 100, 100, 0];
$ar2 = [1, 3, 2, 4];
array_multisort($ar1, $ar2);

var_dump($ar1);
var_dump($ar2);

/*
array(4) {
  [0]=>
  int(0)
  [1]=>
  int(10)
  [2]=>
  int(100)
  [3]=>
  int(100)
}
array(4) {
  [0]=>
  int(4)
  [1]=>
  int(1)
  [2]=>
  int(2)
  [3]=>
  int(3)
}
*/
```

```php
<?php
$ar = [
    ["10", 11, 100, 100, "a"],
    [1, 2, "2", 3, 1]
];

array_multisort($ar[0], SORT_ASC, SORT_STRING,
    $ar[1], SORT_NUMERIC, SORT_DESC);

var_dump($ar);

/*
array(2) {
  [0]=>
  array(5) {
    [0]=>
    string(2) "10"
    [1]=>
    int(100)
    [2]=>
    int(100)
    [3]=>
    int(11)
    [4]=>
    string(1) "a"
  }
  [1]=>
  array(5) {
    [0]=>
    int(1)
    [1]=>
    int(3)
    [2]=>
    string(1) "2"
    [3]=>
    int(2)
    [4]=>
    int(1)
  }
}
*/
```

```php
<?php
$data[] = array(&#039;volume&#039; => 67, &#039;edition&#039; => 2);
$data[] = array(&#039;volume&#039; => 86, &#039;edition&#039; => 1);
$data[] = array(&#039;volume&#039; => 85, &#039;edition&#039; => 6);
$data[] = array(&#039;volume&#039; => 98, &#039;edition&#039; => 2);
$data[] = array(&#039;volume&#039; => 86, &#039;edition&#039; => 6);
$data[] = array(&#039;volume&#039; => 67, &#039;edition&#039; => 7);

$volume  = array_column($data, &#039;volume&#039;);
$edition = array_column($data, &#039;edition&#039;);

array_multisort($volume, SORT_DESC, $edition, SORT_ASC, $data);

print_r($data);

/*
Array
(
    [0] => Array
        (
            [volume] => 98
            [edition] => 2
        )

    [1] => Array
        (
            [volume] => 86
            [edition] => 1
        )

    [2] => Array
        (
            [volume] => 86
            [edition] => 6
        )

    [3] => Array
        (
            [volume] => 85
            [edition] => 6
        )

    [4] => Array
        (
            [volume] => 67
            [edition] => 2
        )

    [5] => Array
        (
            [volume] => 67
            [edition] => 7
        )

)
*/
```

```php
<?php
$data[] = [&#039;volume&#039; => 67, &#039;edition&#039; => 2];
$data[] = [&#039;volume&#039; => 86, &#039;edition&#039; => 7];
$data[] = [&#039;volume&#039; => 85, &#039;edition&#039; => 6];
$data[] = [&#039;volume&#039; => 98, &#039;edition&#039; => 2];
$data[] = [&#039;volume&#039; => 86, &#039;edition&#039; => 6];
$data[] = [&#039;volume&#039; => 67, &#039;edition&#039; => 7];

$volume = array_column($data, &#039;volume&#039;);
$edition = array_column($data, &#039;edition&#039;);

array_multisort($volume, SORT_DESC, $edition, SORT_ASC, $data);

print_r($data);

/*
Array
(
    [0] => Array
        (
            [volume] => 98
            [edition] => 2
        )

    [1] => Array
        (
            [volume] => 86
            [edition] => 6
        )

    [2] => Array
        (
            [volume] => 86
            [edition] => 7
        )

    [3] => Array
        (
            [volume] => 85
            [edition] => 6
        )

    [4] => Array
        (
            [volume] => 67
            [edition] => 2
        )

    [5] => Array
        (
            [volume] => 67
            [edition] => 7
        )

)
*/
```

```php
<?php
$array1 = $array2 = [&#039;Alpha&#039;, &#039;atomic&#039;, &#039;Beta&#039;, &#039;bank&#039;];
$array_lowercase = array_map(&#039;strtolower&#039;, $array1);

array_multisort($array_lowercase, SORT_ASC, SORT_STRING, $array1);

var_dump($array1);

array_multisort($array2, SORT_ASC, SORT_STRING | SORT_FLAG_CASE);

var_dump($array2);

/*
array(4) {
  [0]=>
  string(5) "Alpha"
  [1]=>
  string(6) "atomic"
  [2]=>
  string(4) "bank"
  [3]=>
  string(4) "Beta"
}
array(4) {
  [0]=>
  string(5) "Alpha"
  [1]=>
  string(6) "atomic"
  [2]=>
  string(4) "bank"
  [3]=>
  string(4) "Beta"
}
*/
```

