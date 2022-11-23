```php
array_key_last ( array $array ) : mixed
	
// 注意：php 7.3 才有的函数
// 返回数组第一个键名，空数组返回 null。
```

```php
&lt;?php
$array = [&#039;a&#039; =&gt; 1, &#039;b&#039; =&gt; 2, &#039;c&#039; =&gt; 3];

$res = array_key_last($array);

var_dump($res);

/*
string(1) &quot;c&quot;
*/
```

**如果是老版 php，请用下面函数代替**

```php
if (!function_exists(&quot;array_key_last&quot;)) {
    function array_key_last($array)
    {
        if (!is_array($array) || empty($array)) {
            return NULL;
        }

        return array_keys($array)[count($array) - 1];
    }
}
```