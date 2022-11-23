```php
array_fill_keys ( array $keys , mixed $value ) : array
```
1. 非法键名将强制转化为字符串

```php
&lt;?php
$keys = array(&#039;foo&#039;, 5, 10, &#039;bar&#039;);
$a = array_fill_keys($keys, &#039;banana&#039;);
print_r($a);

/*
Array
(
    [foo] =&gt; banana
    [5] =&gt; banana
    [10] =&gt; banana
    [bar] =&gt; banana
)
*/
```