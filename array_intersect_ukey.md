```php
array_intersect_ukey ( array $array1 , array $array2 [, array $... ], callable $key_compare_func ) : array
```

1. 首先按照自定义的回调函数进行排序
2. 第一个数组的元素和第二个数组元素集合依次比较
3. 比较的是键，使用自定义函数进行比较，如果相等则这个元素被放置到返回数组中，否则继续比较。
4. 比较的时候如果键相等，就开始下次循环比较，并且从第一个数组中下一个元素开始比较。

```php
&lt;?php
function key_compare_func($key1, $key2)
{
    echo(str_pad($key1, 10) . &#039; - &#039; . $key2 . &quot;\n&quot;);

    if ($key1 == $key2){
        return 0;
    }

    if ($key1 &gt; $key2){
        return 1;
    }

    return -1;
}

$array1 = array(&#039;blue&#039; =&gt; 1, &#039;red&#039; =&gt; 2, &#039;green&#039; =&gt; 3, &#039;purple&#039; =&gt; 4);
$array2 = array(&#039;green&#039; =&gt; 5, &#039;blue&#039; =&gt; 6, &#039;yellow&#039; =&gt; 7, &#039;cyan&#039; =&gt; 8);

var_dump(array_intersect_ukey($array1, $array2, &#039;key_compare_func&#039;));
/*
blue       - red
red        - green
blue       - green
red        - purple
green      - purple
green      - blue
yellow     - blue
green      - yellow
yellow     - cyan
green      - cyan
blue       - cyan
blue       - blue
green      - cyan
green      - green
purple     - yellow
red        - yellow
array(2) {
  [&quot;blue&quot;]=&gt;
  int(1)
  [&quot;green&quot;]=&gt;
  int(3)
}
*/
```