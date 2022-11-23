```php
array_key_first ( array $array ) : mixed

// 注意：php 7.3 才有的函数
// 返回数组第一个键名，空数组返回 null。
```

```php
&lt;?php
$array = [&#039;a&#039; =&gt; 1, &#039;b&#039; =&gt; 2, &#039;c&#039; =&gt; 3];

$firstKey = array_key_first($array);

var_dump($firstKey);

/*
string(1) &quot;a&quot;
*/
```

**如果是老版 php，请用下面函数代替**

```php
if (!function_exists(&#039;array_key_first&#039;)) {
    function array_key_first(array $arr) {
        foreach($arr as $key =&gt; $unused) {
            return $key;
        }
        return NULL;
    }
}
```