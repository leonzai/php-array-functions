```php
array_rand ( array $array [, int $num = 1 ] ) : mixed
```

1. 它使用了不适合加密目的的伪随机数生成器。

```php
&lt;?php
$input = array(&quot;Neo&quot;, &quot;Morpheus&quot;, &quot;Trinity&quot;, &quot;Cypher&quot;, &quot;Tank&quot;);
$rand_key = array_rand($input, 1);
$rand_keys = array_rand($input, 2);
var_dump($rand_key);
var_dump($rand_keys);

/*
int(2)
array(2) {
  [0]=&gt;
  int(1)
  [1]=&gt;
  int(4)
}
*/
```