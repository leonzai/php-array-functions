```php
usort ( array &$array , callable $value_compare_func ) : bool
	
// 自定义函数的返回值应该返回一个整数，如果不是整数将转化成整数。
```

```php
<?php
function cmp($a, $b)
{
    if ($a == $b) {
        return 0;
    }
    return ($a < $b) ? -1 : 1;
}

$a = [3, 2, 5, 6, 1];

usort($a, "cmp");

foreach ($a as $key => $value) {
    echo "$key: $value\n";
}

echo "此时等同于 sort";

/*
0: 1
1: 2
2: 3
3: 5
4: 6
此时等同于 sort
*/
```

```php
<?php

class TestObj
{
    public string $name;

    function __construct($name)
    {
        $this->name = $name;
    }

    public static function cmp_obj($a, $b)
    {
        $al = strtolower($a->name);
        $bl = strtolower($b->name);
        if ($al == $bl) {
            return 0;
        }
        return ($al > $bl) ? +1 : -1;
    }
}

$a[] = new TestObj("c");
$a[] = new TestObj("b");
$a[] = new TestObj("d");

usort($a, ["TestObj", "cmp_obj"]);

foreach ($a as $item) {
    echo $item->name . "\n";
}

/*
b
c
d

*/
```

```php
<?php
function my_sort($a, $b)
{
    if ($a == $b) {
        return 0;
    }

    if ($a % 2 == 0 && $b % 2 == 0) {
        return $a < $b ? -1 : 1;
    }
    if ($a % 2 == 0) {
        return 1;
    }
    if ($b % 2 == 0) {
        return -1;
    }

    return $a < $b ? -1 : 1;
}

$a = array(22, 57, 55, 12, 87, 56, 54, 11);
usort($a, "my_sort");


for ($x = 0; $x < count($a); $x++) {
    var_dump($a[$x]);
}

/*
int(11)
int(55)
int(57)
int(87)
int(12)
int(22)
int(54)
int(56)
*/
```