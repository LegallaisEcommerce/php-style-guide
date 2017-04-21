# Legallais PHP Style Guide

## Table of contents

1. [Blocks](#blocks)

## Blocks
```php
// Bad
if(test)
{
    return false;
}
else {
    return true;
}

// Bad
if (test) :
    return false;
else :
    return true;
endif;

// Good
if (test) {
    return false;
} else {
    return true;
}

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