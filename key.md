```php
key ( array $array ) : mixed
```

1. 如果数组是空数组或者指针超出了数组的长度，函数返回 NULL。

```php
&lt;?php
$array = [
    &#039;fruit1&#039; =&gt; &#039;apple&#039;,
    &#039;fruit2&#039; =&gt; &#039;orange&#039;,
    &#039;fruit3&#039; =&gt; &#039;grape&#039;,
    &#039;fruit4&#039; =&gt; &#039;apple&#039;,
    &#039;fruit5&#039; =&gt; &#039;apple&#039;
];

while ($fruit_name = current($array)) {
    if ($fruit_name == &#039;apple&#039;) {
        echo key($array) . &quot;\n&quot;;
    }
    next($array);
}

/*
fruit1
fruit4
fruit5
*/
```