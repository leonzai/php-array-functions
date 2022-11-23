```php
range ( mixed $start , mixed $end [, number $step = 1 ] ) : array
```

```php
<?php
foreach (range(0, 12) as $number) {
    echo $number;
}
echo "\n";

foreach (range(0, 100, 10) as $number) {
    echo $number;
}
echo "\n";

foreach (range('a', 'i') as $letter) {
    echo $letter;
}
echo "\n";

foreach (range('c', 'a') as $letter) {
    echo $letter;
}

/*
0123456789101112
0102030405060708090100
abcdefghi
cba
*/
```