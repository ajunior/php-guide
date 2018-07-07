# String

- [Single Quoted](#single-quoted)
- [Double Quoted](#double-quoted)
- [Heredoc Syntax](#heredoc-syntax)
- [Nowdoc Syntax](#nowdoc-syntax)
- [String Functions](#string-functions)
  - [explode()](#explode)
  - [implode()](#implode)

## Single Quoted
---

```php
$variable = 'lorem ipsum';
var_dump($variable);
```

```php
$variable = 'lorem
ipsum';
var_dump($variable);
//=>
// string(11) "lorem
// ipsum"
```

```php
$variable = 'lorem\' ipsum';
var_dump($variable); //=> string(12) "lorem' ipsum"
```

```php
$variable = 'lorem \\\' ipsum';
var_dump($variable); //=> string(14) "lorem \' ipsum"
```

```php
$variable = 'lorem \n ipsum';
var_dump($variable); //=> string(14) "lorem \n ipsum"
echo $variable;      //=> lorem \n ipsum
```

## Double Quoted
---

```php
$variable = "lorem ipsum";
var_dump($variable); //=> string(11) "lorem ipsum"
```

```php
$variable = "lorem \n ipsum";
var_dump($variable);
//=>
// string(13) "lorem 
//  ipsum"
echo $variable;
//=>
// lorem 
//  ipsum
```

```php
$name = 'fulano';
$hello = 'Hello $name';
var_dump($hello); //=> string(11) "Hello $name"

$hello = "Hello $name";
var_dump($hello); //=> string(12) "Hello fulano"

$hello = "Hello {$name}";
var_dump($hello); //=> string(12) "Hello fulano"

$name = ['name' => 'fulano'];
$hello = "Hello {$name['name']}";
var_dump($hello); //=> string(12) "Hello fulano"

$name = 'name';
var_dump("2 {$name}s"); //=> string(7) "2 names"
```

## Heredoc Syntax
---

```php
$variable = <<<EOD
lorem
ipsum
EOD;

var_dump($variable);
//=>
// string(11) "lorem
// ipsum"
```

```php
$variable = "lorem
\tipsum";

var_dump($variable);
//=>
// string(12) "lorem
// 	ipsum"
```

```php
$name = 'fulano';

$variable = <<<EOD 
Hello $name
EOD;
//=> PHP Parse error:  syntax error, unexpected '<<' (T_SL) in php
```

## Nowdoc Syntax
---

```php

$variable = <<<'EOD'
Hello world!
EOD;

var_dump($variable); //=> string(12) "Hello world!"
```

```php
$name = 'fulano';

$variable = <<<'EOD' 
Hello $name
EOD;
//=> Parse error: syntax error, unexpected '<<' (T_SL) in php
```

## [String Functions](http://php.net/manual/en/book.strings.php)
---

### explode()

```php
$name = "fulano, sicrano";
$names = explode(", ", $names);
var_dump($names);
//=>
// array(2) {
//   [0]=>
//   string(6) "fulano"
//   [1]=>
//   string(7) "sicrano"
// }
```

### implode()

```php
$names = ['fulano', 'sicrano'];
$names = implode(', ', $names);
var_dump($names); //=> string(15) "fulano, sicrano"
```

### strlen()

```php
var_dump(strlen('lorem')); //=> int(5)
```