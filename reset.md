```php
reset ( array &amp;$array ) : mixed
```

1. 如果数组是空数组，函数返回 false。

```php
&lt;?php

$array = array(&#039;step one&#039;, &#039;step two&#039;, &#039;step three&#039;, &#039;step four&#039;);

echo current($array) . &quot;\n&quot;;

next($array);
next($array);
echo current($array) . &quot;\n&quot;;

reset($array);
echo current($array) . &quot;\n&quot;; 

/*
step one
step three
step one

*/
```