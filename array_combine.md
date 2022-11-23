```php
array_combine( array $keys, array $values) : array

// 第一个数组里的值都作为新数组的键名
// 第二个数组里的值都作为新数组的值
// 如果两个参数的数组长度不相等，返回 false 并且爆出警告
```

```php
&lt;?php
$a = array(&#039;green&#039;, &#039;red&#039;, &#039;yellow&#039;);
$b = array(&#039;avocado&#039;, &#039;apple&#039;, &#039;banana&#039;);
$c = array_combine($a, $b);
var_dump($c);

/*
array(3) {
  [&quot;green&quot;]=&gt;
  string(7) &quot;avocado&quot;
  [&quot;red&quot;]=&gt;
  string(5) &quot;apple&quot;
  [&quot;yellow&quot;]=&gt;
  string(6) &quot;banana&quot;
}
*/

class User
{
    public $name = &quot;xxx&quot;;

    public function __toString()
    {
        return $this-&gt;name;
    }
}

$a = array(new User(),);
$b = array(&#039;avocado&#039;,);
$c = array_combine($a, $b);
var_dump($c);

/*
array(1) {
  [&quot;xxx&quot;]=&gt;
  string(7) &quot;avocado&quot;
}
*/
```