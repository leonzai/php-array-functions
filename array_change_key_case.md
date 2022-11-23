```php
array_change_key_case ( array $array [, int $case] ) : array

// $array：需要处理的数组
// $case：必须是 CASE_UPPER 或者 CASE_LOWER，默认是 CASE_LOWER
```

```php
<?php
    
$array = ["FirSt" =&gt; 1, "SecOnd" =&gt; 4];
$result = array_change_key_case($array, CASE_UPPER);
var_dump($result);

/*
array(2) {
  ["FIRST"]=&gt;
  int(1)
  ["SECOND"]=&gt;
  int(4)
}
*/
```
