```php
array_pad ( array $array , int $size , mixed $value ) : array
```

1. $size 是正数，就把 $value 填充到右边，负数则填充到左边。最多一次填充个数为 1048576。

```php
&lt;?php
$input = array(12, 10, 9);

$result = array_pad($input, 5, 0);
// result is array(12, 10, 9, 0, 0)

$result = array_pad($input, -7, -1);
// result is array(-1, -1, -1, -1, 12, 10, 9)

$result = array_pad($input, 2, &quot;noop&quot;);
// not padded
```