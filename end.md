```php
end ( array &amp;$array ) : mixed
```

1. 如果数组是空数组，函数返回 false。

```php
&lt;?php

$fruits = array(&#039;apple&#039;, &#039;banana&#039;, &#039;cranberry&#039;);
echo end($fruits); // cranberry
```