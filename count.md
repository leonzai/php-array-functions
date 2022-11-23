```php
count ( mixed $array_or_countable [, int $mode = COUNT_NORMAL ] ) : int
```

1. 第二个参数默认值 COUNT_NORMAL，表示计算最外面一层数组的长度。还可以是 COUNT_RECURSIVE，将会递归计算数组的长度。

```php
&lt;?php
$food = array(&#039;fruits&#039; =&gt; array(&#039;orange&#039;, &#039;banana&#039;, &#039;apple&#039;),
    &#039;veggie&#039; =&gt; array(&#039;carrot&#039;, &#039;collard&#039;, &#039;pea&#039;));

echo count($food, COUNT_RECURSIVE); // output 8

echo count($food); // output 2
```