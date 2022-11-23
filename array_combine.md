```php
array_combine( array $keys, array $values) : array

// 第一个数组里的值都作为新数组的键名
// 第二个数组里的值都作为新数组的值
// 如果两个参数的数组长度不相等，返回 false 并且爆出警告
```

```php
<?php
$a = array('green', 'red', 'yellow');
$b = array('avocado', 'apple', 'banana');
$c = array_combine($a, $b);
var_dump($c);

/*
array(3) {
  ["green"]=>
  string(7) "avocado"
  ["red"]=>
  string(5) "apple"
  ["yellow"]=>
  string(6) "banana"
}
*/

class User
{
    public $name = "xxx";

    public function __toString()
    {
        return $this->name;
    }
}

$a = array(new User(),);
$b = array('avocado',);
$c = array_combine($a, $b);
var_dump($c);

/*
array(1) {
  ["xxx"]=>
  string(7) "avocado"
}
*/
```