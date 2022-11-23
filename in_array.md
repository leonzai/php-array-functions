```php
in_array ( mixed $needle , array $haystack [, bool $strict = FALSE ] ) : bool
```

1. needle 中文翻译是针，haystack 中文翻译是草。草里寻针。
2. 第一个参数是字符串的话，就是保证大小写也要一致才算匹配成功。
3. 第三个参数是 true 代表全等才算匹配成功，默认是 false，表示只要相等，不管类型是否一样就是匹配成功。

```php
&lt;?php
$a = [[&#039;p&#039;, &#039;h&#039;], [&#039;p&#039;, &#039;r&#039;], &#039;o&#039;];

if (in_array([&#039;p&#039;, &#039;h&#039;], $a)) {
    echo &quot;&#039;ph&#039; was found\n&quot;;
}

if (in_array([&#039;f&#039;, &#039;i&#039;], $a)) {
    echo &quot;&#039;fi&#039; was found\n&quot;;
}

if (in_array(&#039;o&#039;, $a)) {
    echo &quot;&#039;o&#039; was found\n&quot;;
}

/*
&#039;ph&#039; was found
&#039;o&#039; was found
*/
```