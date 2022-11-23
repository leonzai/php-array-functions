```php
array_multisort ( array &amp;$array1 [, mixed $array1_sort_order = SORT_ASC [, mixed $array1_sort_flags = SORT_REGULAR [, mixed $... ]]] ) : bool
    
// 字符串索引将被保留，数字索引会被重新索引。
// $array1 被排序的数组
// $array1_sort_order 指定排序的方向，默认是升序 SORT_ASC，还可以是降序 SORT_DESC。
// $array1_sort_flags 参数等同于 sort 的第二个参数，详情参考 sort 第二个参数。
    
// 这个函数定义的不是很好，具体我们看下面的例子。
```

```php
&lt;?php
$ar1 = [10, 100, 100, 0];
$ar2 = [1, 3, 2, 4];
array_multisort($ar1, $ar2);

var_dump($ar1);
var_dump($ar2);

/*
array(4) {
  [0]=&gt;
  int(0)
  [1]=&gt;
  int(10)
  [2]=&gt;
  int(100)
  [3]=&gt;
  int(100)
}
array(4) {
  [0]=&gt;
  int(4)
  [1]=&gt;
  int(1)
  [2]=&gt;
  int(2)
  [3]=&gt;
  int(3)
}
*/
```

```php
&lt;?php
$ar = [
    [&quot;10&quot;, 11, 100, 100, &quot;a&quot;],
    [1, 2, &quot;2&quot;, 3, 1]
];

array_multisort($ar[0], SORT_ASC, SORT_STRING,
    $ar[1], SORT_NUMERIC, SORT_DESC);

var_dump($ar);

/*
array(2) {
  [0]=&gt;
  array(5) {
    [0]=&gt;
    string(2) &quot;10&quot;
    [1]=&gt;
    int(100)
    [2]=&gt;
    int(100)
    [3]=&gt;
    int(11)
    [4]=&gt;
    string(1) &quot;a&quot;
  }
  [1]=&gt;
  array(5) {
    [0]=&gt;
    int(1)
    [1]=&gt;
    int(3)
    [2]=&gt;
    string(1) &quot;2&quot;
    [3]=&gt;
    int(2)
    [4]=&gt;
    int(1)
  }
}
*/
```

```php
&lt;?php
$data[] = array(&#039;volume&#039; =&gt; 67, &#039;edition&#039; =&gt; 2);
$data[] = array(&#039;volume&#039; =&gt; 86, &#039;edition&#039; =&gt; 1);
$data[] = array(&#039;volume&#039; =&gt; 85, &#039;edition&#039; =&gt; 6);
$data[] = array(&#039;volume&#039; =&gt; 98, &#039;edition&#039; =&gt; 2);
$data[] = array(&#039;volume&#039; =&gt; 86, &#039;edition&#039; =&gt; 6);
$data[] = array(&#039;volume&#039; =&gt; 67, &#039;edition&#039; =&gt; 7);

$volume  = array_column($data, &#039;volume&#039;);
$edition = array_column($data, &#039;edition&#039;);

array_multisort($volume, SORT_DESC, $edition, SORT_ASC, $data);

print_r($data);

/*
Array
(
    [0] =&gt; Array
        (
            [volume] =&gt; 98
            [edition] =&gt; 2
        )

    [1] =&gt; Array
        (
            [volume] =&gt; 86
            [edition] =&gt; 1
        )

    [2] =&gt; Array
        (
            [volume] =&gt; 86
            [edition] =&gt; 6
        )

    [3] =&gt; Array
        (
            [volume] =&gt; 85
            [edition] =&gt; 6
        )

    [4] =&gt; Array
        (
            [volume] =&gt; 67
            [edition] =&gt; 2
        )

    [5] =&gt; Array
        (
            [volume] =&gt; 67
            [edition] =&gt; 7
        )

)
*/
```

```php
&lt;?php
$data[] = [&#039;volume&#039; =&gt; 67, &#039;edition&#039; =&gt; 2];
$data[] = [&#039;volume&#039; =&gt; 86, &#039;edition&#039; =&gt; 7];
$data[] = [&#039;volume&#039; =&gt; 85, &#039;edition&#039; =&gt; 6];
$data[] = [&#039;volume&#039; =&gt; 98, &#039;edition&#039; =&gt; 2];
$data[] = [&#039;volume&#039; =&gt; 86, &#039;edition&#039; =&gt; 6];
$data[] = [&#039;volume&#039; =&gt; 67, &#039;edition&#039; =&gt; 7];

$volume = array_column($data, &#039;volume&#039;);
$edition = array_column($data, &#039;edition&#039;);

array_multisort($volume, SORT_DESC, $edition, SORT_ASC, $data);

print_r($data);

/*
Array
(
    [0] =&gt; Array
        (
            [volume] =&gt; 98
            [edition] =&gt; 2
        )

    [1] =&gt; Array
        (
            [volume] =&gt; 86
            [edition] =&gt; 6
        )

    [2] =&gt; Array
        (
            [volume] =&gt; 86
            [edition] =&gt; 7
        )

    [3] =&gt; Array
        (
            [volume] =&gt; 85
            [edition] =&gt; 6
        )

    [4] =&gt; Array
        (
            [volume] =&gt; 67
            [edition] =&gt; 2
        )

    [5] =&gt; Array
        (
            [volume] =&gt; 67
            [edition] =&gt; 7
        )

)
*/
```

```php
&lt;?php
$array1 = $array2 = [&#039;Alpha&#039;, &#039;atomic&#039;, &#039;Beta&#039;, &#039;bank&#039;];
$array_lowercase = array_map(&#039;strtolower&#039;, $array1);

array_multisort($array_lowercase, SORT_ASC, SORT_STRING, $array1);

var_dump($array1);

array_multisort($array2, SORT_ASC, SORT_STRING | SORT_FLAG_CASE);

var_dump($array2);

/*
array(4) {
  [0]=&gt;
  string(5) &quot;Alpha&quot;
  [1]=&gt;
  string(6) &quot;atomic&quot;
  [2]=&gt;
  string(4) &quot;bank&quot;
  [3]=&gt;
  string(4) &quot;Beta&quot;
}
array(4) {
  [0]=&gt;
  string(5) &quot;Alpha&quot;
  [1]=&gt;
  string(6) &quot;atomic&quot;
  [2]=&gt;
  string(4) &quot;bank&quot;
  [3]=&gt;
  string(4) &quot;Beta&quot;
}
*/
```

