```php
uasort ( array &amp;$array , callable $value_compare_func ) : bool
```

```php
&lt;?php
function cmp($a, $b)
{
    if ($a == $b) {
        return 0;
    }
    return ($a &lt; $b) ? -1 : 1;
}

$array = [&#039;a&#039; =&gt; 4, &#039;b&#039; =&gt; 8, &#039;c&#039; =&gt; -1, &#039;d&#039; =&gt; -9,];
uasort($array, &#039;cmp&#039;);

print_r($array);

/*
Array
(
    [d] =&gt; -9
    [c] =&gt; -1
    [a] =&gt; 4
    [b] =&gt; 8
)
*/
```