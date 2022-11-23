```php
array_fill ( int $start_index , int $num , mixed $value ) : array
```

```php
&lt;?php
$a = array_fill(5, 6, &#039;banana&#039;);
$b = array_fill(-2, 4, &#039;pear&#039;);
print_r($a);
print_r($b);

/*
Array
(
    [5] =&gt; banana
    [6] =&gt; banana
    [7] =&gt; banana
    [8] =&gt; banana
    [9] =&gt; banana
    [10] =&gt; banana
)
Array
(
    [-2] =&gt; pear
    [0] =&gt; pear
    [1] =&gt; pear
    [2] =&gt; pear
)
*/
```