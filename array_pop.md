```php
array_pop ( array &amp;$array ) : mixed
```

1. 空数组返回 NULL。
2. 函数运行完，数组内部指针将返回到数组头部。

```php
&lt;?php
$stack = [&quot;a&quot;, &quot;b&quot;, &quot;c&quot;, &quot;d&quot;];
$fruit = array_pop($stack);
var_dump($fruit);
var_dump($stack);

/*
string(1) &quot;d&quot;
array(3) {
  [0]=&gt;
  string(1) &quot;a&quot;
  [1]=&gt;
  string(1) &quot;b&quot;
  [2]=&gt;
  string(1) &quot;c&quot;
}
*/
```