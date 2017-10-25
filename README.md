# about
About PHP Class Collection

# classes

## php-cc/std
```php
namespace PCC\Standard;

class StandardClass;

```

## php-cc/validate
```php
namespace PCC\Validate;

interface ValidatorInterface;
class SomeValidator extends StandardClass implements ValidatorInterface;
// Some = { Int, String, Float, Bool }. Adding new validator is quite easy.

class RegexValidator extends StringValidator;
```

## php-cc/enum
```php
namespace PCC/Enumeration;

class Enum extends StandardClass;
class SomeEnum extends Enum;

class UniqueEnum extends Enum;
class SomeUniqueEnum extends UniqueEnum;

// Some = { Int, String }. Adding new enum is quite easy.
```

## php-cc/collection
```php
namespace PCC/Collection;

abstract class Collection implements Traversable;
class SomeCollection extends Collection;
// Some = { Int, String }. Adding new enum is quite easy.
```
