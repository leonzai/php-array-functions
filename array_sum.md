```php
array_sum ( array $array ) : number
```

1. 空数组返回 0。

```php
&lt;?php
$a = [2, 4, 6, 8];
echo &quot;数组 a 求和：&quot; . array_sum($a) . &quot;\n&quot;;

$b = [&quot;a&quot; =&gt; 1.2, &quot;b&quot; =&gt; 2.3, &quot;c&quot; =&gt; 3.4];
echo &quot;数组 b 求和：&quot; . array_sum($b) . &quot;\n&quot;;

echo &quot;数组 a 求平均数：&quot; . array_sum($a) / count($a);

/*
数组 a 求和：20
数组 b 求和：6.9
数组 a 求平均数：5
*/
```