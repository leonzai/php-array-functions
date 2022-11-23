```php
uksort ( array &amp;$array , callable $key_compare_func ) : bool
```

```php
&lt;?php
function cmp($a, $b)
{
    return strcasecmp($a, $b);
}

$a = [&quot;John&quot; =&gt; 1, &quot;Earth&quot; =&gt; 2, &quot;apple&quot; =&gt; 3, &quot;banana&quot; =&gt; 4];

uksort($a, &quot;cmp&quot;);

foreach ($a as $key =&gt; $value) {
    echo &quot;$key: $value\n&quot;;
}

/*
apple: 3
banana: 4
Earth: 2
John: 1

*/
```