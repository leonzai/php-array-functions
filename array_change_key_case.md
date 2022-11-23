```php
array_change_key_case ( array $array [, int $case] ) : array

// $array：需要处理的数组
// $case：必须是 CASE_UPPER 或者 CASE_LOWER，默认是 CASE_LOWER
```

```php
<?php
    
$array = ["FirSt" => 1, "SecOnd" => 4];
$result = array_change_key_case($array, CASE_UPPER);
var_dump($result);

/*
array(2) {
  ["FIRST"]=>
  int(1)
  ["SECOND"]=>
  int(4)
}
*/
```