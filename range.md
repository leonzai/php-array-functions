```php
range ( mixed $start , mixed $end [, number $step = 1 ] ) : array
```

```php
&lt;?php
foreach (range(0, 12) as $number) {
    echo $number;
}
echo &quot;\n&quot;;

foreach (range(0, 100, 10) as $number) {
    echo $number;
}
echo &quot;\n&quot;;

foreach (range(&#039;a&#039;, &#039;i&#039;) as $letter) {
    echo $letter;
}
echo &quot;\n&quot;;

foreach (range(&#039;c&#039;, &#039;a&#039;) as $letter) {
    echo $letter;
}

/*
0123456789101112
0102030405060708090100
abcdefghi
cba
*/
```