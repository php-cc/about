# about
About PHP Class Collection

# classes

```php
// php-cc/std
namespace PCC\Std;
class StandardClass;

// php-cc/validate
namespace PHPCC\Validate
interface ValidatorInterface;
class IntValidator extends StandardClass implements ValidatorInterface;
class StringValidator extends StandardClass implements ValidatorInterface;
class RegexValidator extends StringValidator;

```
