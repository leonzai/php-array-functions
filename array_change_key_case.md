```php
array_change_key_case ( array $array [, int $case] ) : array

// $array：需要处理的数组
// $case：必须是 CASE_UPPER 或者 CASE_LOWER，默认是 CASE_LOWER
```

```php
&lt;?php
    
$array = [&quot;FirSt&quot; =&gt; 1, &quot;SecOnd&quot; =&gt; 4];
$result = array_change_key_case($array, CASE_UPPER);
var_dump($result);

/*
array(2) {
  [&quot;FIRST&quot;]=&gt;
  int(1)
  [&quot;SECOND&quot;]=&gt;
  int(4)
}
*/
```
