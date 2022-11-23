```php
usort ( array &amp;$array , callable $value_compare_func ) : bool
	
// 自定义函数的返回值应该返回一个整数，如果不是整数将转化成整数。
```

```php
&lt;?php
function cmp($a, $b)
{
    if ($a == $b) {
        return 0;
    }
    return ($a &lt; $b) ? -1 : 1;
}

$a = [3, 2, 5, 6, 1];

usort($a, &quot;cmp&quot;);

foreach ($a as $key =&gt; $value) {
    echo &quot;$key: $value\n&quot;;
}

echo &quot;此时等同于 sort&quot;;

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
&lt;?php

class TestObj
{
    public string $name;

    function __construct($name)
    {
        $this-&gt;name = $name;
    }

    public static function cmp_obj($a, $b)
    {
        $al = strtolower($a-&gt;name);
        $bl = strtolower($b-&gt;name);
        if ($al == $bl) {
            return 0;
        }
        return ($al &gt; $bl) ? +1 : -1;
    }
}

$a[] = new TestObj(&quot;c&quot;);
$a[] = new TestObj(&quot;b&quot;);
$a[] = new TestObj(&quot;d&quot;);

usort($a, [&quot;TestObj&quot;, &quot;cmp_obj&quot;]);

foreach ($a as $item) {
    echo $item-&gt;name . &quot;\n&quot;;
}

/*
b
c
d

*/
```

```php
&lt;?php
function my_sort($a, $b)
{
    if ($a == $b) {
        return 0;
    }

    if ($a % 2 == 0 &amp;&amp; $b % 2 == 0) {
        return $a &lt; $b ? -1 : 1;
    }
    if ($a % 2 == 0) {
        return 1;
    }
    if ($b % 2 == 0) {
        return -1;
    }

    return $a &lt; $b ? -1 : 1;
}

$a = array(22, 57, 55, 12, 87, 56, 54, 11);
usort($a, &quot;my_sort&quot;);


for ($x = 0; $x &lt; count($a); $x++) {
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