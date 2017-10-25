# about
About PHP Class Collection

# classes

## php-cc/std
Provide basic magic methods such as `__get`, `__set`, `__call` and `__callStatic` to prevent unintended dynamic property insertion and to give parent method such as `parent::__get` for derived classes.
```php
namespace PCC\Standard;

class StandardClass {
    public function __get( string $name ) { throw new InaccessiblePropertyException( static::class, $name ); }
    /* ... */
}
```

```php
/**
 * @property string $someProperty
 */
class YourClass extends StandardClass {
    private $valueOfSomeProperty;
    public function __get( string $name ) {
        if( $name === 'someProperty' ) return $this->valueOfSomeProperty;
        return parent::__get( $name );      // always throws InaccessiblePropertyException
    }
}
```

## php-cc/validate
```php
namespace PCC\Validate;

interface ValidatorInterface {
    public function validate( $value ) : bool;
}
class SomeValidator extends StandardClass implements ValidatorInterface;
// Some = { Int, String, Float, Bool }. Adding new validator is quite easy.

class RegexValidator extends StringValidator;

interface ValidatorAwareInterface;
```

```php
class YourValidator implements ValidatorInterface {
    public function validate( $value ) : bool {
        if( /* $value is valid */ ) return true;
        return false;
    }
}
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
