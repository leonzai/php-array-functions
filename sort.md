```php
sort ( array &amp;$array [, int $sort_flags = SORT_REGULAR ] ) : bool

// 如果比较的两个元素相等，那么他们俩的顺序是不可预测的。
// 该函数返回值是 true 表示排序成功，false 表示排序失败。
```

| 第二个参数                   | 解释                                                         |
| ---------------------------- | ------------------------------------------------------------ |
| **`SORT_REGULAR`**（默认值） | 正常比较，不转化类型，**注意，使用该参数时，数组中的类型应当是同一种，否则会出现意想不到的结果** |
| **`SORT_NUMERIC`**           | 先转化成数字再进行比较                                       |
| **`SORT_STRING`**            | 先转化成字符串再比较                                         |
| **`SORT_LOCALE_STRING`**     | 根据当前的区域（locale）设置，作为字符串比较，比方说拼音 a 有四个音节，第一声将排在第二声前面 |
| **`SORT_NATURAL`**           | 人类友好的方式排序，`"a2"` `"a12"` `"c1"` `"c12"`，先按照`字母`排序，`字母`相同的时就按后面的`数值整体`做排序，即: `a2 < a12 < c1 < c12` |
| **`SORT_FLAG_CASE`**         | `SORT_FLAG_CASE`主要配合 `SORT_STRING` 和 `SORT_NATURAL`对`字符`处理时是否忽略大小写 |

```php
&lt;?php
// 错误示例：当没有指定排序的时候一定要是同一类型， 不是同一类型会出现问题
$fruits = array(&quot;a&quot;, &quot;b&quot;, &quot;heiheihei&quot; =&gt; &quot;A&quot;, &quot;1&quot;, 1, 2, &quot;2&quot;);
sort($fruits);

foreach ($fruits as $key =&gt; $val) {
    echo &quot;$key -- $val\n&quot;;
}

/*
0 -- 1
1 -- A
2 -- a
3 -- b
4 -- 1
5 -- 2
6 -- 2
*/

// 全是字符串：字符串型数字最先，大写中间，小写最后
$fruits = array(&quot;ac&quot;, &quot;aC&quot;, &quot;b&quot;, &quot;heiheihei&quot; =&gt; &quot;A&quot;, &quot;101&quot;, &quot;-101&quot;, &quot;2&quot;, &quot;1.2&quot;, &quot;2.2&quot;, &quot;ab&quot;);
sort($fruits);

foreach ($fruits as $key =&gt; $val) {
    echo &quot;$key -- $val\n&quot;;
}

/*
0 -- -101
1 -- 1.2
2 -- 2
3 -- 2.2
4 -- 101
5 -- A
6 -- aC
7 -- ab
8 -- ac
9 -- b
*/
```

```php
&lt;?php
$fruits = array(&#039;1c&#039;, &#039;a1&#039;, &#039;11b&#039;);
sort($fruits, SORT_NUMERIC);

foreach ($fruits as $key =&gt; $val) {
    echo &quot;转化成数字：&quot; . (int)$val . &#039;----&#039;;
    echo &quot; $val\n&quot;;
}

/*
转化成数字：0---- a1
转化成数字：1---- 1c
转化成数字：11---- 11b
*/
```

```php
&lt;?php
$fruits = array(2, 15, 5, 3, &#039;a&#039;, &#039;A&#039;);
sort($fruits, SORT_STRING);

foreach ($fruits as $key =&gt; $val) {
    echo &quot;$key -- $val\n&quot;;
}

/*
0 -- 15
1 -- 2
2 -- 3
3 -- 5
4 -- A
5 -- a
*/
```

```php
&lt;?php
$fruits = array(&#039;a1&#039;, &#039;a12&#039;, &#039;c1&#039;, &#039;c12&#039;, &#039;c2&#039;, &#039;c10&#039;);
sort($fruits, SORT_NATURAL);

foreach ($fruits as $key =&gt; $val) {
    echo &quot;$key -- $val\n&quot;;
}

/*
0 -- a1
1 -- a12
2 -- c1
3 -- c2
4 -- c10
5 -- c12
*/
```

```php
&lt;?php
$fruits = array(
    &quot;Orange1&quot;, &quot;orange2&quot;, &quot;Orange3&quot;, &quot;orange20&quot;
);
sort($fruits, SORT_NATURAL | SORT_FLAG_CASE);
foreach ($fruits as $key =&gt; $val) {
    echo $val . &quot;\n&quot;;
}

/*
Orange1
orange2
Orange3
orange20
*/

sort($fruits, SORT_NATURAL);
foreach ($fruits as $key =&gt; $val) {
    echo $val . &quot;\n&quot;;
}

/*
Orange1
Orange3
orange2
orange20
*/
```