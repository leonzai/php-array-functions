```php
array_product ( array $array ) : number
```

1. 空数组返回 1，php 5.3.6 之前返回 0。

```php
<?php

$a = array(2, 4, 6, 8);
echo array_product($a) . "\n";
echo array_product(array()) . "\n";

/*
384
1
*/
```