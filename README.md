# GtinValidation

[![Build Status](https://travis-ci.org/ryanblak/GtinValidation.svg)](https://travis-ci.org/ryanblak/GtinValidation)
[![License](https://poser.pugx.org/ryanblak/gtinvalidation/license)](https://packagist.org/packages/ryanblak/gtinvalidation)

GtinValidation is a library for validating the format and check digit of a GTIN.

## Requirements

- PHP 5.4 or higher

## Installation

You can find GtinValidation on [Packagist](https://packagist.org/packages/ryanblak/gtinvalidation).
To install GtinValidation in [Composer](https://getcomposer.org/):

```json
{
  "require": {
    "ryanblak/gtinvalidation": "dev-master"
  }
}
```

## Usage

### Basic check

To check a GTIN's validity:

```php
<?php

use GtinValidation\GtinValidator;

$gtinValidator = new GtinValidator('0000000000000');
echo $gtinValidator->isValid();
```

Output

```
false
```

### Advanced Check

To get more detailed information about the GTIN and its validity, retrieve the GTIN object:

```php
<?php

use GtinValidation\GtinValidator;

$gtinValidator = new GtinValidator('0000000000000');
$gtinObject = $gtinValidator->getGtinObject();

echo $gtinObject->getType() . PHP_EOL;
echo $gtinObject->isValidFormat() . PHP_EOL;
echo $gtinObject->isValid() . PHP_EOL;
```

Output

```
GTIN-13
true
false
```
