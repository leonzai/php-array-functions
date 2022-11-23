```php
array_chunk ( array $array , int $size [, bool $preserve_keys] ) : array

// $array：需要处理的数组
// $size：每个块包含几个元素
// $preserve_keys：必须是 true 或者 false，默认是 false
```

```php
<?php

$array = [&#039;a&#039; => 1, &#039;b&#039; => 2, &#039;c&#039; => 3];
$result = array_chunk($array, 2);
var_dump($result);

/*
array(2) {
  [0]=>
  array(2) {
    [0]=>
    int(1)
    [1]=>
    int(2)
  }
  [1]=>
  array(1) {
    [0]=>
    int(3)
  }
}
*/

$array = [&#039;a&#039; => 1, &#039;b&#039; => 2, &#039;c&#039; => 3];
$result = array_chunk($array, 2, true);
var_dump($result);

/*
array(2) {
  [0]=>
  array(2) {
    ["a"]=>
    int(1)
    ["b"]=>
    int(2)
  }
  [1]=>
  array(1) {
    ["c"]=>
    int(3)
  }
}
*/
```