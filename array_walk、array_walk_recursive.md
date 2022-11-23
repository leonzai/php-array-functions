```php
array_walk ( array &amp;$array , callable $callback [, mixed $userdata = NULL ] ) : bool
```

1. 第一个参数是要被处理的数组
2. 第二个参数是回调函数。只有一个参数时，该参数被依次赋值为数组元素的值。如果是两个参数，该参数被依次赋值为数组元素的值、数组元素的索引。如果有第三个参数，赋值为 array_walk 的第三个参数。
3. 第三个参数可选，用于赋值给回调函数的第三个参数。
4. 返回值是布尔值。
5. 该函数只能用来修改数组元素的值，不应该用来修改数组的结构或者元素的键等等。

```php
&lt;?php
$arr = [
    &quot;name1&quot; =&gt; &#039;栗深.com&#039;,
    &quot;name2&quot; =&gt; &#039;lishengroup.com&#039;,
    &quot;name3&quot; =&gt; &#039;qianjinyike.com&#039;,
];

/** foreach 方式 */
foreach ($arr as $key =&gt; $value) {
    $newKey = substr($key, 4);
    echo &quot;$newKey: $value\n&quot;;
}

/** array_walk 方式 */
array_walk($arr, function ($value, $key) {
    $newKey = substr($key, 4);
    echo &quot;$newKey: $value\n&quot;;
});
```

```php
&lt;?php
$arr = [
    &quot;name2&quot; =&gt; [&#039;lishengroup.com&#039;, &#039;栗深&#039;],
    &quot;name3&quot; =&gt; &#039;qianjinyike.com&#039;,
];

array_walk($arr, function ($value) {
    var_dump($value);
});

/*
array(2) {
  [0]=&gt;
  string(15) &quot;lishengroup.com&quot;
  [1]=&gt;
  string(6) &quot;栗深&quot;
}
string(15) &quot;qianjinyike.com&quot;
*/

array_walk_recursive($arr, function ($value) {
    var_dump($value);
});

/*
string(15) &quot;lishengroup.com&quot;
string(6) &quot;栗深&quot;
string(15) &quot;qianjinyike.com&quot;
*/
```

