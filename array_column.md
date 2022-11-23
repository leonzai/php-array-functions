```php
array_column ( array $input , mixed $column_key [, mixed $index_key = NULL ] ) : array

// 第一个参数可以是一维数组或是多维数组，也可以是对象数组
// 第二个参数可以是数组索引、数组键名、属性名称、null
// 第三个参数设置返回的数组的键
```

```php
&lt;?php

$arr = [
    [&#039;id&#039; =&gt; 11, &#039;name&#039; =&gt; &#039;a&#039;,],
    [&#039;id&#039; =&gt; 12, &#039;name&#039; =&gt; &#039;a&#039;,],
];
$result = array_column($arr, &#039;name&#039;);
var_dump($result);

/*
array(2) {
  [0]=&gt;
  string(1) &quot;a&quot;
  [1]=&gt;
  string(1) &quot;a&quot;
}
*/

$arr = [
    [&#039;id&#039; =&gt; 11, &#039;name&#039; =&gt; &#039;a&#039;,],
    [&#039;id&#039; =&gt; 12, &#039;name&#039; =&gt; &#039;a&#039;,],
];
$result = array_column($arr, &#039;name&#039;, &#039;id&#039;);
var_dump($result);

/*
array(2) {
  [11]=&gt;
  string(1) &quot;a&quot;
  [12]=&gt;
  string(1) &quot;a&quot;
}
*/

$arr = [
    [&#039;id&#039; =&gt; 11, &#039;name&#039; =&gt; &#039;a&#039;,],
    [&#039;id&#039; =&gt; 12, &#039;name&#039; =&gt; &#039;a&#039;,],
];
$result = array_column($arr, null, &#039;id&#039;);
var_dump($result);

/*
array(2) {
  [11]=&gt;
  array(2) {
    [&quot;id&quot;]=&gt;
    int(11)
    [&quot;name&quot;]=&gt;
    string(1) &quot;a&quot;
  }
  [12]=&gt;
  array(2) {
    [&quot;id&quot;]=&gt;
    int(12)
    [&quot;name&quot;]=&gt;
    string(1) &quot;a&quot;
  }
}
*/

class User
{
    public $username;

    public function __construct(string $username)
    {
        $this-&gt;username = $username;
    }
}

$users = [
    new User(&#039;user 1&#039;),
    new User(&#039;user 2&#039;),
];

$result = array_column($users, &#039;username&#039;);
var_dump($result);

/*
array(2) {
  [0]=&gt;
  string(6) &quot;user 1&quot;
  [1]=&gt;
  string(6) &quot;user 2&quot;
}
*/
```