```php
array_chunk ( array $array , int $size [, bool $preserve_keys] ) : array

// $array：需要处理的数组
// $size：每个块包含几个元素
// $preserve_keys：必须是 true 或者 false，默认是 false
```

```php
&lt;?php

$array = [&#039;a&#039; =&gt; 1, &#039;b&#039; =&gt; 2, &#039;c&#039; =&gt; 3];
$result = array_chunk($array, 2);
var_dump($result);

/*
array(2) {
  [0]=&gt;
  array(2) {
    [0]=&gt;
    int(1)
    [1]=&gt;
    int(2)
  }
  [1]=&gt;
  array(1) {
    [0]=&gt;
    int(3)
  }
}
*/

$array = [&#039;a&#039; =&gt; 1, &#039;b&#039; =&gt; 2, &#039;c&#039; =&gt; 3];
$result = array_chunk($array, 2, true);
var_dump($result);

/*
array(2) {
  [0]=&gt;
  array(2) {
    [&quot;a&quot;]=&gt;
    int(1)
    [&quot;b&quot;]=&gt;
    int(2)
  }
  [1]=&gt;
  array(1) {
    [&quot;c&quot;]=&gt;
    int(3)
  }
}
*/
```