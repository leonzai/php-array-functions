```php
rsort ( array &amp;$array [, int $sort_flags = SORT_REGULAR ] ) : bool
```
与 `sort` 函数的**唯一区别**是：排序的方向不同。

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
rsort($fruits);

foreach ($fruits as $key =&gt; $val) {
    echo &quot;$key = $val\n&quot;;
}

/*
0 = orange
1 = lemon
2 = banana
3 = apple
*/
```