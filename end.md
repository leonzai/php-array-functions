```php
end ( array &$array ) : mixed
```

1. 如果数组是空数组，函数返回 false。

```php
<?php

$fruits = array('apple', 'banana', 'cranberry');
echo end($fruits); // cranberry
```