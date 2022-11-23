```php
list ( mixed $var1 [, mixed $... ] ) : array
```

1. php 7.1.0 之前只能对数字索引数组生效，并且也假定数组索引从 0 开始。
2. php 5 的时候，从最右侧开始赋值。php 7 从最左侧开始赋值。这是针对提取值给数组而言，如果是普通变量就不用操心，具体看例子。

```php
<?php
$info = [&#039;coffee&#039;, &#039;brown&#039;, &#039;caffeine&#039;];

list($drink, $color, $power) = $info;
echo "$drink  $color  $power \n";

list($drink, , $power) = $info;
echo "$drink  $power.\n";

list( , , $power) = $info;
echo "$power\n";

list($bar) = "abcde";
var_dump($bar); // NULL

/*
coffee  brown  caffeine 
coffee  caffeine.
caffeine
NULL
*/
```

```php
<?php
list($a, list($b, $c)) = [1, [2, 3]];

var_dump($a, $b, $c);

/*
int(1)
int(2)
int(3)
*/
```

```php
<?php

$info = array(&#039;coffee&#039;, &#039;brown&#039;, &#039;caffeine&#039;);

list($a[0], $a[1], $a[2]) = $info;

var_dump($a);

/*
php7：

array(3) {
  [0]=>
  string(6) "coffee"
  [1]=>
  string(5) "brown"
  [2]=>
  string(8) "caffeine"
}

php5：

array(3) {
  [2]=>
  string(8) "caffeine"
  [1]=>
  string(5) "brown"
  [0]=>
  string(6) "coffee"
}
*/
```

```php
<?php
$foo = array(2 => &#039;a&#039;, &#039;foo&#039; => &#039;b&#039;, 0 => &#039;c&#039;);
$foo[1] = &#039;d&#039;;
list($x, $y, $z) = $foo;
var_dump($x, $y, $z);

/*
string(1) "c"
string(1) "d"
string(1) "a"
*/
```

# php 7.1 开始

```php
<?php
$data = [
    ["id" => 1, "name" => &#039;Tom&#039;],
    ["id" => 2, "name" => &#039;Fred&#039;],
];
foreach ($data as ["id" => $id, "name" => $name]) {
    echo "id: $id, name: $name\n";
}
list(1 => $second, 3 => $fourth) = [1, 2, 3, 4];
echo "$second, $fourth\n";

/*
id: 1, name: Tom
id: 2, name: Fred
2, 4
*/
```