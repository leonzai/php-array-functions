```php
array_column ( array $input , mixed $column_key [, mixed $index_key = NULL ] ) : array

// 第一个参数可以是一维数组或是多维数组，也可以是对象数组
// 第二个参数可以是数组索引、数组键名、属性名称、null
// 第三个参数设置返回的数组的键
```

```php
<?php

$arr = [
    [&#039;id&#039; => 11, &#039;name&#039; => &#039;a&#039;,],
    [&#039;id&#039; => 12, &#039;name&#039; => &#039;a&#039;,],
];
$result = array_column($arr, &#039;name&#039;);
var_dump($result);

/*
array(2) {
  [0]=>
  string(1) "a"
  [1]=>
  string(1) "a"
}
*/

$arr = [
    [&#039;id&#039; => 11, &#039;name&#039; => &#039;a&#039;,],
    [&#039;id&#039; => 12, &#039;name&#039; => &#039;a&#039;,],
];
$result = array_column($arr, &#039;name&#039;, &#039;id&#039;);
var_dump($result);

/*
array(2) {
  [11]=>
  string(1) "a"
  [12]=>
  string(1) "a"
}
*/

$arr = [
    [&#039;id&#039; => 11, &#039;name&#039; => &#039;a&#039;,],
    [&#039;id&#039; => 12, &#039;name&#039; => &#039;a&#039;,],
];
$result = array_column($arr, null, &#039;id&#039;);
var_dump($result);

/*
array(2) {
  [11]=>
  array(2) {
    ["id"]=>
    int(11)
    ["name"]=>
    string(1) "a"
  }
  [12]=>
  array(2) {
    ["id"]=>
    int(12)
    ["name"]=>
    string(1) "a"
  }
}
*/

class User
{
    public $username;

    public function __construct(string $username)
    {
        $this->username = $username;
    }
}

$users = [
    new User(&#039;user 1&#039;),
    new User(&#039;user 2&#039;),
];

$result = array_column($users, &#039;username&#039;);
var_dump($result);

/*
array(2) {
  [0]=>
  string(6) "user 1"
  [1]=>
  string(6) "user 2"
}
*/
```