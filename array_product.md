```php
array_product ( array $array ) : number
```

1. 空数组返回 1，php 5.3.6 之前返回 0。

```php
&lt;?php

$a = array(2, 4, 6, 8);
echo array_product($a) . &quot;\n&quot;;
echo array_product(array()) . &quot;\n&quot;;

/*
384
1
*/
```