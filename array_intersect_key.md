```php
array_intersect_key ( array $array1 , array $array2 [, array $... ] ) : array
```

1. 比较采用规则：if (string) $elem1 === (string) $elem2

```php
&lt;?php
$array1 = array(&#039;blue&#039;  =&gt; 1, &#039;red&#039;  =&gt; 2, &#039;green&#039;  =&gt; 3, &#039;purple&#039; =&gt; 4);
$array2 = array(&#039;green&#039; =&gt; 5, &#039;blue&#039; =&gt; 6, &#039;yellow&#039; =&gt; 7, &#039;cyan&#039;   =&gt; 8);

var_dump(array_intersect_key($array1, $array2));

/*
array(2) {
  [&quot;blue&quot;]=&gt;
  int(1)
  [&quot;green&quot;]=&gt;
  int(3)
}
*/
```