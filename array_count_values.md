```php
array_count_values( array $array) : array
```

```php
&lt;?php

$array = array(1, &quot;hello&quot;, 1, &quot;world&quot;, &quot;hello&quot;);
$result = array_count_values($array);
var_dump($result);

/*
array(3) {
  [1]=&gt;
  int(2)
  [&quot;hello&quot;]=&gt;
  int(2)
  [&quot;world&quot;]=&gt;
  int(1)
}
*/

# 计算某个键值对出现的次数
$list = [
    [&#039;id&#039; =&gt; 1, &#039;userId&#039; =&gt; 5],
    [&#039;id&#039; =&gt; 2, &#039;userId&#039; =&gt; 5],
    [&#039;id&#039; =&gt; 3, &#039;userId&#039; =&gt; 6],
];

echo array_count_values(array_column($list, &#039;userId&#039;))[5];

/*
2
*/
```