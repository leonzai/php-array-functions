```php
ksort ( array &amp;$array [, int $sort_flags = SORT_REGULAR ] ) : bool
```
与 `sort` 函数的**唯一区别**是：ksort 使用键名排序，返回数组保留键名，而 sort 排序的是数组元素的值，返回数组不再保留键名。

**第二个参数效果完全等同于 sort，请参考**

[https://qianjinyike.com/【sort】排序数组（不再保留键名）](https://qianjinyike.com/【sort】排序数组（不再保留键名） "https://qianjinyike.com/【sort】排序数组（不再保留键名）")

```php
&lt;?php
$fruits = [
    &quot;d&quot; =&gt; &quot;lemon&quot;,
    &quot;a&quot; =&gt; &quot;orange&quot;,
    &quot;b&quot; =&gt; &quot;banana&quot;,
    &quot;c&quot; =&gt; &quot;apple&quot;,
];
ksort($fruits);

foreach ($fruits as $key =&gt; $val) {
    echo &quot;$key = $val\n&quot;;
}

/*
a = orange
b = banana
c = apple
d = lemon
*/
```