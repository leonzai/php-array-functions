```php
array_flip ( array $array ) : array
```

```php
&lt;?php
$input = array(&quot;a&quot; =&gt; 1, &quot;b&quot; =&gt; 1, &quot;c&quot; =&gt; 2);
$flipped = array_flip($input);

var_dump($flipped);

/*
array(2) {
  [1]=&gt;
  string(1) &quot;b&quot;
  [2]=&gt;
  string(1) &quot;c&quot;
}
*/
```