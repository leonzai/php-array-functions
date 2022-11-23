```php
array_unique ( array $array [, int $sort_flags = SORT_STRING ] ) : array
```

1. 参数 sort_flags 的值可以是 SORT_REGULAR、SORT_NUMERIC、SORT_STRING、SORT_LOCALE_STRING，产生的效果等同于 sort 第二个参数，请参考 [https://qianjinyike.com/【sort】排序数组（不再保留键名）](https://qianjinyike.com/【sort】排序数组（不再保留键名） "https://qianjinyike.com/【sort】排序数组（不再保留键名）")
2. 第二个参数值默认为 SORT_STRING。
3. 函数保留键名。
4. 如果两个元素相等，保留第一个出现的元素。
5. 比较方式： `if (string) $elem1 === (string) $elem2`
6. php 7.2 之前，返回的数组里的数字索引将被重新索引，字符串索引不变，参考下面例子。

```php
&lt;?php
$input = [&quot;a&quot; =&gt; &quot;green&quot;, &quot;red&quot;, &quot;b&quot; =&gt; &quot;green&quot;, &quot;red&quot;, &quot;blue&quot;,];

$result = array_unique($input);
print_r($result);

$result = array_flip(array_flip($input)); // 如果不关心键，那么这种方式比上面的快很多。
var_dump($result);

/*
// php 7.2 开始
Array
(
    [a] =&gt; green
    [0] =&gt; red
    [2] =&gt; blue
)
array(3) {
  [&quot;b&quot;]=&gt;
  string(5) &quot;green&quot;
  [1]=&gt;
  string(3) &quot;red&quot;
  [2]=&gt;
  string(4) &quot;blue&quot;
}
*/

/*
// php 7.2 之前
Array
(
    [a] =&gt; green
    [0] =&gt; red
    [1] =&gt; blue
)
array(3) {
  [&quot;b&quot;]=&gt;
  string(5) &quot;green&quot;
  [2]=&gt;
  string(3) &quot;red&quot;
  [1]=&gt;
  string(4) &quot;blue&quot;
}
*/
```

```php
&lt;?php
$input = [4, &quot;4&quot;, &quot;3&quot;, 4, 3, &quot;3&quot;];
$result = array_unique($input);
var_dump($result);

/*
array(2) {
  [0]=&gt;
  int(4)
  [2]=&gt;
  string(1) &quot;3&quot;
}
*/
```