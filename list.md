```php
list ( mixed $var1 [, mixed $... ] ) : array
```

1. php 7.1.0 之前只能对数字索引数组生效，并且也假定数组索引从 0 开始。
2. php 5 的时候，从最右侧开始赋值。php 7 从最左侧开始赋值。这是针对提取值给数组而言，如果是普通变量就不用操心，具体看例子。

```php
&lt;?php
$info = [&#039;coffee&#039;, &#039;brown&#039;, &#039;caffeine&#039;];

list($drink, $color, $power) = $info;
echo &quot;$drink  $color  $power \n&quot;;

list($drink, , $power) = $info;
echo &quot;$drink  $power.\n&quot;;

list( , , $power) = $info;
echo &quot;$power\n&quot;;

list($bar) = &quot;abcde&quot;;
var_dump($bar); // NULL

/*
coffee  brown  caffeine 
coffee  caffeine.
caffeine
NULL
*/
```

```php
&lt;?php
list($a, list($b, $c)) = [1, [2, 3]];

var_dump($a, $b, $c);

/*
int(1)
int(2)
int(3)
*/
```

```php
&lt;?php

$info = array(&#039;coffee&#039;, &#039;brown&#039;, &#039;caffeine&#039;);

list($a[0], $a[1], $a[2]) = $info;

var_dump($a);

/*
php7：

array(3) {
  [0]=&gt;
  string(6) &quot;coffee&quot;
  [1]=&gt;
  string(5) &quot;brown&quot;
  [2]=&gt;
  string(8) &quot;caffeine&quot;
}

php5：

array(3) {
  [2]=&gt;
  string(8) &quot;caffeine&quot;
  [1]=&gt;
  string(5) &quot;brown&quot;
  [0]=&gt;
  string(6) &quot;coffee&quot;
}
*/
```

```php
&lt;?php
$foo = array(2 =&gt; &#039;a&#039;, &#039;foo&#039; =&gt; &#039;b&#039;, 0 =&gt; &#039;c&#039;);
$foo[1] = &#039;d&#039;;
list($x, $y, $z) = $foo;
var_dump($x, $y, $z);

/*
string(1) &quot;c&quot;
string(1) &quot;d&quot;
string(1) &quot;a&quot;
*/
```

# php 7.1 开始

```php
&lt;?php
$data = [
    [&quot;id&quot; =&gt; 1, &quot;name&quot; =&gt; &#039;Tom&#039;],
    [&quot;id&quot; =&gt; 2, &quot;name&quot; =&gt; &#039;Fred&#039;],
];
foreach ($data as [&quot;id&quot; =&gt; $id, &quot;name&quot; =&gt; $name]) {
    echo &quot;id: $id, name: $name\n&quot;;
}
list(1 =&gt; $second, 3 =&gt; $fourth) = [1, 2, 3, 4];
echo &quot;$second, $fourth\n&quot;;

/*
id: 1, name: Tom
id: 2, name: Fred
2, 4
*/
```