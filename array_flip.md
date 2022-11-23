```php
array_flip ( array $array ) : array
```

```php
<?php
$input = array("a" => 1, "b" => 1, "c" => 2);
$flipped = array_flip($input);

var_dump($flipped);

/*
array(2) {
  [1]=>
  string(1) "b"
  [2]=>
  string(1) "c"
}
*/
```