```php
reset ( array &$array ) : mixed
```

1. 如果数组是空数组，函数返回 false。

```php
<?php

$array = array('step one', 'step two', 'step three', 'step four');

echo current($array) . "\n";

next($array);
next($array);
echo current($array) . "\n";

reset($array);
echo current($array) . "\n"; 

/*
step one
step three
step one

*/
```