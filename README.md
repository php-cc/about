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

interface ValidatorAwareInterface;
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

abstract class Collection extends StandardClass implements Traversable {
    abstract protected function getValidator( ) : ValidatorInterface;
}
```

## php-cc/map
```php
namespace PCC/Map;

abstract class Map extends Collection;
```

## php-cc/vector
```php
namespace PCC/Vector;

abstract class Vector extends Collection;
class SomeVector extends Collection;
// Some = { Int, String, Float, Bool }. Adding new collectio is quite easy.

```
