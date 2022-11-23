```php
array_intersect ( array $array1 , array $array2 [, array $... ] ) : array
```

```php
&lt;?php
$array1 = array(&quot;a&quot; =&gt; &quot;green&quot;, &quot;red&quot;, &quot;blue&quot;);
$array2 = array(&quot;b&quot; =&gt; &quot;green&quot;, &quot;yellow&quot;, &quot;red&quot;);
$result = array_intersect($array1, $array2);

var_dump($result);

/*
array(2) {
  [&quot;a&quot;]=&gt;
  string(5) &quot;green&quot;
  [0]=&gt;
  string(3) &quot;red&quot;
}
*/

&lt;?php
$array1 = array(&quot;a&quot; =&gt; &quot;green&quot;, &quot;green&quot;, &quot;blue&quot;);
$array2 = array(&quot;b&quot; =&gt; &quot;green&quot;, &quot;yellow&quot;, &quot;red&quot;);
$result = array_intersect($array1, $array2);

var_dump($result);

/*
array(2) {
  [&quot;a&quot;]=&gt;
  string(5) &quot;green&quot;
  [0]=&gt;
  string(5) &quot;green&quot;
}
*/
```
