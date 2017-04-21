# Legallais PHP Style Guide

## Table of contents

1. [Blocks](#blocks)
1. [Whitespace](#whitespace)

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