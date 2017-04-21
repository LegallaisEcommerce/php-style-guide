# Legallais PHP Style Guide

## Table of contents

1. [Blocks](#blocks)
1. [Whitespace](#whitespace)
1. [Arrays](#arrays)
1. [Variables](#variables)
1. [Naming](#naming)

## Blocks

- Use braces with all multi-line blocks.

```php
// Bad
if (test)
    return false;

// Good 
if (test) return false;

// Good 
if (test) {
    return false;
}
```

-  If you're using multi-line blocks with if and else, put else on the same line as your if block's closing brace. Opening brace should be on the same line as your if statement.

```php
// Bad
if(test)
{
    return false;
}
else {
    return true;
}

// Good
if (test) {
    return false;
} else {
    return true;
}
```
-  Don't use alternative syntax (colon tags).

```php
// Bad
if (test) :
    return false;
else :
    return true;
endif;
```
-  Use ternary operators only for small tests.

```php
// Bad
$foo = ($bar <= 3) || ($bar >= 12) ? $baz->getLongMethodName() : $baz->getAnotherLongMethodName();

// Good
$foo = $bar ? true : false;

```

## Whitespace
- Use soft tabs (space character) set to 4 spaces

```php
// Bad
function foo() {
∙∙return true;
}

// Good
function foo() {
∙∙∙∙return true;
}

```

- Place 1 space before the leading brace

```php
// Bad
function foo(){
    return true;
}

// Good
function foo() {
    return true;
}
```

- Add a line break before leading brace for class and methods

```php
// Bad
class Foo {

    public function bar() {
	
    }
}

// Good
class Foo
{

    public function bar()
    {
	
    }
}
```

- Place 1 after the comma between arguments

```php
// Bad
function foo($bar,$baz) {
    return true;
}

// Good
function foo($bar, $baz) {
    return true;
}
```

- Do not add spaces inside parentheses.

```php
// Bad
function foo( $bar ) {
    return true;
}

// Good
function foo($bar) {
    return true;
}
```

## Arrays

- Use brackets syntax.

```php
// Bad
$myArray = array(
    'foo' => 'bar',
);

// Good
$myArray = [
    'foo' => 'bar',
];
```

- Align values with `=>` sign. There are plugins to do that for your favorite editor.

```php
// Bad
$myArray = [
    'foo' => 'bar';
    'myArrayKey' => 'baz',
];

// Good
$myArray = [
    'foo'        => 'bar',
    'myArrayKey' => 'baz',
];
```

- Do not align your array keys with the opening bracket.

```php
// Bad
$var->longMethodName()->anotherLongMethodName() = [
                                                        'foo'        => 'bar',
                                                        'myArrayKey' => 'baz',
                                                   ];

// Good
$var->longMethodName()->anotherLongMethodName() = [
    'foo'        => 'bar',
    'myArrayKey' => 'baz',
];
```

- Break lines if array is longer than one pair of key => value.

```php
// Bad
$myArray = ['foo' => 'bar', 'myArrayKey' => 'baz'];

// Good
$myArray = [
    'foo'        => 'bar',
    'myArrayKey' => 'baz',
];

// Good
$myArray = ['foo' => 'bar'];
```

- Always put a comma after values, even on last one.

```php
// Bad
$myArray = [
    'foo'        => 'bar',
    'myArrayKey' => 'baz'
];

// Good
$myArray = [
    'foo'        => 'bar',
    'myArrayKey' => 'baz',
];
```

- To push an item to an array, avoid `array_push` *Why ? Easier to read and quicker to execute*

```php
// Bad
$myArray = [];
 
foreach ($foo as $bar) {
   array_push($myArray, $bar);
}

// Good
$myArray = [];
 
foreach ($foo as $bar) {
   $myArray[] = $bar;
}

```

## Variables

- Align values with `=` symbol.

```php
// Bad
$foo = 'hello';
$fooBarBaz = 'world';

// Good
$foo       = 'hello';
$fooBarBaz = 'world';
```

- Keep lines short.

```php
// Bad
$foo = $this->getEntityManager()->getRepository('Foo\Entity\Foo')->findOneBy(['name' => 'bar']);

// Good
$fooRepository = $this->getEntityManager()->getRepository('Foo\Entity\Foo');
$foo           = $fooRepository->findOneBy(['name' => 'bar']);
```



## Naming

- Use explicit methods and variables names.

```php
// Bad
$toto = true;

// Bad
$p = $this->getProduct($pid);

// Good
$product = $this->getProduct($productId);
```

- Use lower camelCase for variable and method names.

```php
// Bad
public function get_productid()
{

}

// Good
public function getProductId()
{

}

// Bad
$Productid = $this->getProductId();

// Good
$productId = $this->getProductId();

```


- Use upper camelCase class names.

```php
// Bad
class myClass
{

}

// Good
class MyClass
{

}
```

- Use param_case for `protected` and `private`.

```php
// Bad
protected $myVar;
private $OtherVar;

// Good
protected $my_var;
private $other_var;
```

- Use CONSTANT_CASE for `constant`.

```php
// Bad
const FooBar = 42;

// Good
const FOO_BAR = 42;
```

- Use lowercase for logical operators.

```php
// Bad
$foo = TRUE;
$bar = FALSE;
$baz = NULL;

// Good
$foo = true;
$bar = false;
$baz = null;
```

- Dont repeat object name in methods

```php
// Bad
class Product
{
    public function setProductTitle($title)
    {
	
    }
}

$product      = new Product();
$productTitle = $product->setProductTitle('Product Title');

// Good
class Product
{
    public function setTitle($title)
    {
	
    }
}

$product      = new Product();
$productTitle = $product->setTitle('Product Title');
```