```php
array_intersect_assoc ( array $array1 , array $array2 [, array $... ] ) : array
```

1. 键名和值比较都采用规则：if (string) $elem1 === (string) $elem2，如果键名不相等，不会转换和比较值。

```php
&lt;?php
$array1 = array(&quot;a&quot; =&gt; &quot;green&quot;, &quot;b&quot; =&gt; &quot;brown&quot;, &quot;c&quot; =&gt; &quot;blue&quot;, &quot;red&quot;, &#039;name&#039; =&gt; &quot;&quot;);
$array2 = array(&quot;a&quot; =&gt; &quot;green&quot;, &quot;b&quot; =&gt; &quot;yellow&quot;, &quot;blue&quot;, &quot;red&quot;, &quot;name&quot; =&gt; false);
$result = array_intersect_assoc($array1, $array2);
var_dump($result);

/*
array(2) {
  [&quot;a&quot;]=&gt;
  string(5) &quot;green&quot;
  [&quot;name&quot;]=&gt;
  string(0) &quot;&quot;
}
*/
```