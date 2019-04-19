# PHP coding conventions

Tuân theo chuẩn PSR (PHP Standards Recommendation) của nhóm FIG

```Comments
https://www.php-fig.org/psr/
https://github.com/php-fig/fig-standards/tree/master/accepted
```

## PSR-1 Basic Coding Standard

===================================================================================================================
```link
https://www.php-fig.org/psr/psr-1/
```

### 1.1 Files

#### 1.1.1 PHP tags

- Code phải được viết trong cặp thẻ <?php ?> và nên sử dụng cặp thẻ ngắn <?= ?> thay cho echo. Không sử dụng các thẻ khác

#### 1.1.2 Character Encoding

- Code chỉ được sử dụng UTF-8 không có BOM (BOM - Byte Order Mark là các chuỗi EF,BB,BF ở đầu file cho phép phần mềm biết đây là 1 file UTF-8).

#### 1.1.3 Side Effects

- Mỗi một file PHP chỉ nên làm 1 nhiệm vụ duy nhất ( chứa một class, chứa functions, hoặc chứa constants ... ), tránh chồng chéo (gọi là side effect).

### 1.2 Namespace and Class Names

- Namespace phải tuân theo chuẩn PSR “autoloading” (PSR-0, PSR-4).
- Tên của class phải trùng với tên file chứa class 

~~~php
<?php
// PHP 5.3 and later:
namespace Vendor\Model;

class Foo
{
}
~~~

- Tên class phải viết theo quy tắc StudlyCaps.
- Code viết cho PHP 5.2.x và phiên bản cũ hơn  phải sử dụng quy ước pseudo-namespacing ( sử dụng `Vendor_` trước trên class )

~~~php
<?php
// PHP 5.2.x and earlier:
class Vendor_Model_Foo
{
}
~~~

### 1.3 Class Constants, Properties, and Methods

#### 1.3.1 Hằng Số
- Các hẳng số phải viết hoa tất cả các chữ, cách nhau bằng dấu gạch chân.

~~~php
<?php
namespace Vendor\Model;

class Foo
{
    const VERSION = '1.0';
    const DATE_APPROVED = '2012-06-01';
}
~~~

#### 1.3.2 Properties

- Tuân thủ theo một quy tắc nhất định, không nên sử dụng nhiều quy ước.

~~~
Quy ước dùng quy tắc camelCase để đặt tên thuộc tính.
~~~

#### 1.3.3 Methods
- Tên phương thức viết theo quy tắc camelCase.

## PSR-2: Coding Style Guide

===================================================================================================================
```link
https://www.php-fig.org/psr/psr-2/
```


### 2.1 General

#### 2.1.1 Basic Coding Standard

- Code phải tuân thủ tất cả chuẩn [PSR-1] & [PSR-0].

#### 2.1.2 Files

- Các file phải sử dụng Unix LF (linefeed) để kết thúc dòng.
- Các file PHP phải kết thúc bằng một dòng trắng.
- Thẻ đóng `?>` không sử dụng ở file chỉ chứ code PHP

#### 2.1.3 Lines

- Trên 1 dòng không vượt quá 120 kí tự, tốt nhất nên nhỏ hơn hoặc bằng 80 kí tự.
- Không nên có kí tự trắng ở cuối dòng code.
- Có thể sử dụng dòng trắng để chia tách các khối để cho view code dễ dàng hơn.
- Không được sử dụng nhiều khai báo, toán tử trên cùng một dòng

#### 2.1.4 Cách đầu dòng

- Sử dụng 4 khoảng trắng(spaces) để thụt dòng, tuyệt đối không dùng tab (bạn có thể khai báo trong công cụ lập trình để khi ấn tab nó tương đương với việc thụt vào 4 spaces).

#### 2.1.5 Keywords and True/False/Null

- Những PHP [keywords] phải viết chữ thường.
- Những hằng số PHP `true`, `false`, và `null` phải viết thường.

[keywords]: http://php.net/manual/en/reserved.keywords.php

### 2.2 Namespace and Use Declarations

- Phải có 1 dòng trắng sau khi khai báo namespace và phải có 1 dòng trắng sau các khai báo use.
- Tất cả những khai báo `use` phải viết sau khai báo `namespace`
- Phải sử dụng từ khóa `use` cho mỗi khai báo
- Phải sủ dụng một dòng trắng sau mỗi khối khai báo `use`

~~~php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

// ... additional PHP code ...

~~~

### 2.3. Classes, Properties, and Methods

#### 2.3.1 Extends and Implements

- Từ khóa `extends` và `implements` phải được sử dụng trên cùng một dòng với [tên class].
- Khai báo thẻ mở và thẻ đóng một class phải ở một dòng riêng biệt.

~~~php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClass implements \ArrayAccess, \Countable
{
    // constants, properties, methods
}
~~~

- Danh sách các `implements` phải được tách ra thành nhiều dòng, mỗi một dòng chứa một khai báo riêng biệt.

~~~php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClass implements
    \ArrayAccess,
    \Countable,
    \Serializable
{
    // constants, properties, methods
}
~~~

#### 2.3.2 Properties

- Không sử dụng từ khóa `var` khi khai báo [property]
- Không được khai báo nhiều hơn một [property] cho mỗi khai báo.
- Tên của [property] không nên dùng gạch dưới để khai báo đặc tính [protected] hay [private]

~~~php
<?php
namespace Vendor\Package;

class ClassName
{
    public $foo = null;
}
~~~

#### 2.3.3 Methods

- Tên của [Method] không nên dùng gạch dưới để khai báo đặc tính [protected] hay [private]
- Tên của [Method] không được có ký tự [space] phía sau khai báo. Ký tự mở [{] và đóng [}] phải được viết ở một dòng riêng biệt, và không được có ký tự [space] sau.

~~~php
<?php
namespace Vendor\Package;

class ClassName
{
    public function fooBarBaz($arg1, &$arg2, $arg3 = [])
    {
        // method body
    }
}
~~~

#### 2.3.4 Method Arguments

- Khi dùng nhiều biến cho [method], không được dùng [space] trước mỗi dấu phẩy, và phải có một [space] sau môi dấu phẩy
- Biến cho [method] có giá trị mặc định thì phải khai báo sau cùng khi khai báo [method]

~~~php
<?php
namespace Vendor\Package;

class ClassName
{
    public function foo($arg1, &$arg2, $arg3 = [])
    {
        // method body
    }
}
~~~

- Biến cho [method] có thể khai báo thành nhiều dòng, mỗi dòng chỉ được khai báo một biến.
- Khi khai báo biến cho [method] trên nhiều dòng, thì ký tự đóng argument [(] và mở method [{] phải được phân tách bằng một [space]

~~~php
<?php
namespace Vendor\Package;

class ClassName
{
    public function aVeryLongMethodName(
        ClassTypeHint $arg1,
        &$arg2,
        array $arg3 = []
    ) {
        // method body
    }
}
~~~

#### 2.3.5 `abstract`, `final`, and `static`

- Khi khai báo các đặc tính `abstract` và `final`  thì phải dùng trước các khai báo `public` và `protected`
- Khi khai báo `static` thì phải khai báo sau các khai báo `public` và `protected`

~~~php
<?php
namespace Vendor\Package;

abstract class ClassName
{
    protected static $foo;

    abstract protected function zim();

    final public static function bar()
    {
        // method body
    }
}
~~~

#### 2.3.6. Method and Function Calls

- Khi khởi tạo một [method] hay gọi [function], không được có ký tự [space] ở giữa [method] hoặc tên [function] và ký tự mở [(], không được có [space] phía trước ký tự đóng [)]
- Trong danh sách các biến không được có [space] trước dấu phẩy, và phải có [space] phía sau dấy phẩy

~~~php
<?php
bar();
$foo->bar($arg1);
Foo::bar($arg2, $arg3);
~~~

- Các biến có thể  phân tách thành nhiều dòng, trường hợp này, mỗi biến phải được trình bày ở một dòng riêng biệt.

~~~php
<?php
$foo->bar(
    $longArgument,
    $longerArgument,
    $muchLongerArgument
);
~~~

### 2.4 Control Structures

- Phải có [space] sau mỗi toán tử chuyển hướng
- There MUST be one space after the control structure keyword
- Không được có [space] sau thẻ mở toán tử  chuyển hướng
- There MUST NOT be a space after the opening parenthesis
- Không được có [space] phía trước thẻ đóng toán tử  chuyển hướng
- Phải có một [space] giữa thẻ đóng [)] và thẻ mở [{]
- There MUST be one space between the closing parenthesis and the opening brace
- Nội dung của [structure] phải được cách lề  hơn so với tên
- Ký tự đóng phải được viết ở dòng tiếp theo so với nội dung, nằm ở dòng mới riêng biệt.
- Nội dung của [structure] phải được bao đóng bởi ký tự ngoặc [{] và [}], điều này giúp cho chuẩn hóa cách tổ  chức code cho [structure] và hạn chế lỗi khi thêm code vào [structure]

#### 2.4.1. `if`, `elseif`, `else`

- Chú ý toán tử  `else` và `elseif` phải được viết cùng một dòng với ký tự đóng điều kiện trước.
- Chú ý các ký tự dấu ngoặc đơn, dấu cách và dấu ngoặc nhọn ở ví dụ sau

~~~php
<?php
if ($expr1) {
    // if body
} elseif ($expr2) {
    // elseif body
} else {
    // else body;
}
~~~

- Không nên dùng toán tử  `else if` , nên thay bằng toán tử  `elseif`.

#### 2.4.2. `switch`, `case`

- Toán tử  `case` phải được sử dụng trong `switch`, và toán tử  `break` phải được đặt ở level trên cùng trong nội dụng của `case`. Bắt buộc phải  comment ở `case` không bình thường, ví dụ `// no break` ở ví dụ sau.
- Chú ý các ký tự dấu ngoặc đơn, dấu cách và dấu ngoặc nhọn ở ví dụ sau:

~~~php
<?php
switch ($expr) {
    case 0:
        echo 'First case, with a break';
        break;
    case 1:
        echo 'Second case, which falls through';
        // no break
    case 2:
    case 3:
    case 4:
        echo 'Third case, return instead of break';
        return;
    default:
        echo 'Default case';
        break;
}
~~~

#### 2.4.3. `while`, `do while`

- Chú ý các ký tự dấu ngoặc đơn, dấu cách và dấu ngoặc nhọn ở ví dụ sau

~~~php
<?php
while ($expr) {
    // structure body
}
~~~

- Chú ý các ký tự dấu ngoặc đơn, dấu cách và dấu ngoặc nhọn ở ví dụ sau

~~~php
<?php
do {
    // structure body;
} while ($expr);
~~~

#### 2.4.4. `for`

- Chú ý các ký tự dấu ngoặc đơn, dấu cách và dấu ngoặc nhọn ở ví dụ sau

~~~php
<?php
for ($i = 0; $i < 10; $i++) {
    // for body
}
~~~

#### 2.4.5. `foreach`

- Chú ý các ký tự dấu ngoặc đơn, dấu cách và dấu ngoặc nhọn ở ví dụ sau

~~~php
<?php
foreach ($iterable as $key => $value) {
    // foreach body
}
~~~

#### 2.4.6. `try`, `catch`

- Chú ý các ký tự dấu ngoặc đơn, dấu cách và dấu ngoặc nhọn ở ví dụ sau

~~~php
<?php
try {
    // try body
} catch (FirstExceptionType $e) {
    // catch body
} catch (OtherExceptionType $e) {
    // catch body
}
~~~

### 2.5 Closures

- Phải có một [space] sau từ khóa `function`, và một [space] phía trước và phía sau từ khóa `use`
- Ký tự mở [{] phải được viết trên cùng dòng, và ký tự đóng phải được viết ở dòng mới.
- Không được có [space] phía sau [)] cùng khai báo tham số , hoặc biến số, và không được có [space] phía trước ký tự mở [(] danh sách tham số, biến số 
- Không được có [space] sau ký tự bắt đầu tham số hoặc biến số [(], và không được có [space] phía trước ký tự đóng tham số hoặc biến số
- Trong danh sách các tham số và biến, không được có [space] sau mỗi dấu phẩy, và phải có một [space] sau mỗi dấu phẩy
- Tham số có giá trị mặc định phải được khai báo ở sau cùng danh sách
- Chú ý các ký tự dấu ngoặc đơn, dấu cách, dấu phẩy và dấu ngoặc nhọn ở ví dụ sau

~~~php
<?php
$closureWithArgs = function ($arg1, $arg2) {
    // body
};

$closureWithArgsAndVars = function ($arg1, $arg2) use ($var1, $var2) {
    // body
};
~~~

- Khi dùng nhiều tham số và biến có thể khai báo ở nhiều dòng, trường hợp này mỗi dòng chỉ có thể chứa một giá trị.
- Khi dùng nhiều tham số hoặc biến số, thì ký tự đóng [)] và ký tự mở hàm [{] phải cùng một dòng, và có một [space] phân tách.

~~~php
<?php
$longArgs_noVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) {
    // body
};

$noArgs_longVars = function () use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
    // body
};

$longArgs_longVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
    // body
};

$longArgs_shortVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) use ($var1) {
    // body
};

$shortArgs_longVars = function ($arg) use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
    // body
};
~~~

- Lưu ý, các quy tắc về format cũng cần được áp dụng khi sử dung [closure] trong [function] dưới dạng tham số

~~~php
<?php
$foo->bar(
    $arg1,
    function ($arg2) use ($var1) {
        // body
    },
    $arg3
);
~~~

### 2.6 Ví dụ Coding Style

~~~php
<?php
namespace Vendor\Package;

use FooInterface;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class Foo extends Bar implements FooInterface
{
    public function sampleMethod($a, $b = null)
    {
        if ($a === $b) {
            bar();
        } elseif ($a > $b) {
            $foo->bar($arg1);
        } else {
            BazClass::bar($arg2, $arg3);
        }
    }

    final public static function bar()
    {
        // method body
    }
}
~~~

## 3. Logger Interface

===================================================================================================================

```link
https://www.php-fig.org/psr/psr-3/
```

### 3.1. Specification

#### 3.1.1 Basics

- `LoggerInterface` đề xuất 8 [method] tạo logs tương ứng với các `mức độ log` [RFC 5424][] (debug, info, notice, warning, error, critical, alert, emergency).
- Phương thức thứ 9, `log`, cho phép `mức độ log` vơi tham số . Khi gọi phương thức này với hằng số  `mức độ log` thì kết quả trả về phải có kế quả trả về phải cùng `mức độ log`. Việc gọi phương thức log với một mức độ không được định nghĩa thì phải trả về  `Psr\Log\InvalidArgumentException`, nếu như không biết mức độ của lỗi. Không nên chỉnh sửa tùy biến mức độ `log`  nếu như không cần thiết cho dự án.

[RFC 5424]: http://tools.ietf.org/html/rfc5424

#### 3.1.2 Message

- Mọi [method] cho phép trả [mesage] thành chuỗi, hoặc một [object] với một [method] trả về  chuỗi `__toString()`. Khi sử dụng có thể  nhận message là một object, nhưng cũng phải hỗ trợ để trả về dạng chuỗi.

- [message] có thể  chứa [placeholders], cho phép người dùng thay thế giá trị dạng [array] trong khi sử dụng
- Tên của [placeholders] phải tương ứng với các khóa nội dung [array] trong ngữ cảnh sử dụng
- [Placeholders] phải bắt đầu bằng ký tự `{`, và kết thúc bằng ký tự `}`, không được có khoảng trắng [space] giữa tên [placeholders] và ký tự này.
- Quy tắc đặt tên [Placeholder], nên chỉ bao gồm các ký tự `A-Z`, `a-z`, `0-9`, gạch chân `_`, và dấu chám `.`.

 Ví dụ tham khảo :
  ~~~php
  <?php

  /**
   * Interpolates context values into the message placeholders.
   */
  function interpolate($message, array $context = array())
  {
      // build a replacement array with braces around the context keys
      $replace = array();
      foreach ($context as $key => $val) {
          // check that the value can be casted to string
          if (!is_array($val) && (!is_object($val) || method_exists($val, '__toString'))) {
              $replace['{' . $key . '}'] = $val;
          }
      }

      // interpolate replacement values into the message and return
      return strtr($message, $replace);
  }

  // a message with brace-delimited placeholder names
  $message = "User {username} created";

  // a context array of placeholder names => replacement values
  $context = array('username' => 'bolivar');

  // echoes "User bolivar created"
  echo interpolate($message, $context);
  ~~~

#### 3.1.3 Context

- Mọi phương thức chấp nhận dữ liệu trong ngữ cảnh là một mảng. Phải đảm bảo dữ liệu truyền vào phải có tính mở. Một dữ liệu truyền vào không được trả về lỗi [error]. hoặc cảnh báo [warning], hay [notice] của PHP.
- Nếu một đối tượng `Exception` gửi vào ngữ cảnh, nó phải chứa khóa `'exception'`. Nó phải cho phép truy xuất lỗi. Vẫn phải xác minh khóa `'exception'` trong một `Exception` trước khi sử dụng.

#### 3.1.4 Tham khảo Helper classes và interfaces

- Có thể sử dụng Class `Psr\Log\AbstractLogger` cho `LoggerInterface`, nó đã được tạo để thỏa mãn quy ước phía trên.
- Tương tự, có thể sử dụng `Psr\Log\LoggerTrait` cho phương thức `log`. Tuy nhiên nó không hỗ trợ `interfaces`, nếu sử dụng bạn vẫn phải kế thừa `LoggerInterface`
- `Psr\Log\NullLogger` cung cấp cả với `interface`.  Nó có thể cung cấp 
- `Psr\Log\LoggerAwareInterface` có chứa phương thức `setLogger(LoggerInterface $logger)`.
- `Psr\Log\LoggerAwareTrait`  có thể sử dụng trong class dạng `$this->logger`.
- `Psr\Log\LogLevel` chứa các `log levels`.

### 3.2. Package tham khảo

[psr/log](https://packagist.org/packages/psr/log) package.

### 3.3. `Psr\Log\LoggerInterface`

~~~php
<?php

namespace Psr\Log;

/**
 * Describes a logger instance.
 *
 * The message MUST be a string or object implementing __toString().
 *
 * The message MAY contain placeholders in the form: {foo} where foo
 * will be replaced by the context data in key "foo".
 *
 * The context array can contain arbitrary data, the only assumption that
 * can be made by implementors is that if an Exception instance is given
 * to produce a stack trace, it MUST be in a key named "exception".
 *
 * See https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-3-logger-interface.md
 * for the full interface specification.
 */
interface LoggerInterface
{
    /**
     * System is unusable.
     *
     * @param string $message
     * @param array $context
     * @return void
     */
    public function emergency($message, array $context = array());

    /**
     * Action must be taken immediately.
     *
     * Example: Entire website down, database unavailable, etc. This should
     * trigger the SMS alerts and wake you up.
     *
     * @param string $message
     * @param array $context
     * @return void
     */
    public function alert($message, array $context = array());

    /**
     * Critical conditions.
     *
     * Example: Application component unavailable, unexpected exception.
     *
     * @param string $message
     * @param array $context
     * @return void
     */
    public function critical($message, array $context = array());

    /**
     * Runtime errors that do not require immediate action but should typically
     * be logged and monitored.
     *
     * @param string $message
     * @param array $context
     * @return void
     */
    public function error($message, array $context = array());

    /**
     * Exceptional occurrences that are not errors.
     *
     * Example: Use of deprecated APIs, poor use of an API, undesirable things
     * that are not necessarily wrong.
     *
     * @param string $message
     * @param array $context
     * @return void
     */
    public function warning($message, array $context = array());

    /**
     * Normal but significant events.
     *
     * @param string $message
     * @param array $context
     * @return void
     */
    public function notice($message, array $context = array());

    /**
     * Interesting events.
     *
     * Example: User logs in, SQL logs.
     *
     * @param string $message
     * @param array $context
     * @return void
     */
    public function info($message, array $context = array());

    /**
     * Detailed debug information.
     *
     * @param string $message
     * @param array $context
     * @return void
     */
    public function debug($message, array $context = array());

    /**
     * Logs with an arbitrary level.
     *
     * @param mixed $level
     * @param string $message
     * @param array $context
     * @return void
     */
    public function log($level, $message, array $context = array());
}
~~~

### 3.4. `Psr\Log\LoggerAwareInterface`

~~~php
<?php

namespace Psr\Log;

/**
 * Describes a logger-aware instance.
 */
interface LoggerAwareInterface
{
    /**
     * Sets a logger instance on the object.
     *
     * @param LoggerInterface $logger
     * @return void
     */
    public function setLogger(LoggerInterface $logger);
}
~~~

### 3.5. `Psr\Log\LogLevel`

~~~php
<?php

namespace Psr\Log;

/**
 * Describes log levels.
 */
class LogLevel
{
    const EMERGENCY = 'emergency';
    const ALERT     = 'alert';
    const CRITICAL  = 'critical';
    const ERROR     = 'error';
    const WARNING   = 'warning';
    const NOTICE    = 'notice';
    const INFO      = 'info';
    const DEBUG     = 'debug';
}

## 4. PSR-4 Autoloader

===================================================================================================================

```link
https://www.php-fig.org/psr/psr-4/
```
~~~

## 1. Overview

This PSR describes a specification for [autoloading][] classes from file paths. It is fully interoperable, and can be used in addition to any other autoloading specification, including [PSR-0][]. This PSR also describes  where to place files that will be autoloaded according to the specification.

## 2. Specification


Tên đầy đủ nó PHẢI có một 'tên lớp kết thúc' (terminating class name)

Tên xác định đầy đủ PHẢI có một namespace gốc.

Tên xác định đầy đủ CÓ THỂ có một hoặc nhiều namespace con.


1. The term "class" refers to classes, interfaces, traits, and other similar structures.

2. Khai báo đầy đủ một `class` có dạng sau 

~~~php
\<NamespaceName>(\<SubNamespaceNames>)*\<ClassName>
~~~

    1. The fully qualified class name MUST have a top-level namespace name, also known as a "vendor namespace".
    1. Khai báo phải có [namespace] của mức cá nhất, có thể hiểu là [vendor namespace]

    2. The fully qualified class name MAY have one or more sub-namespace names.
    2. Khai báo đầy thể có thể có một hoặc nhiều [namespace] con

    3. The fully qualified class name MUST have a terminating class name.

    4. Underscores have no special meaning in any portion of the fully qualified class name.

    5. Alphabetic characters in the fully qualified class name MAY be any combination of lower case and upper case.

    6. All class names MUST be referenced in a case-sensitive fashion.

3. When loading a file that corresponds to a fully qualified class name ...
3. Khi lấy file 

    1. A contiguous series of one or more leading namespace and sub-namespace names, not including the leading namespace separator, in the fully qualified class name (a "namespace prefix") corresponds to at least one
       "base directory".
    1. Một chuỗi liên tục bao gồm [namespace], và [sub-namespace], không được có dấu phân tách [namespace], 

    2. The contiguous sub-namespace names after the "namespace prefix" correspond to a subdirectory within a "base directory", in which the namespace separators represent directory separators. The subdirectory name MUST match the case of the sub-namespace names.

    3. The terminating class name corresponds to a file name ending in `.php`. The file name MUST match the case of the terminating class name.

4. Sử dụng [Autoloader] không được trả về lỗi, không được đưa ra bất kỳ lỗi nào, không trả về giá trị

## 3. Examples

The table below shows the corresponding file path for a given fully qualified
class name, namespace prefix, and base directory.

| Fully Qualified Class Name    | Namespace Prefix   | Base Directory           | Resulting File Path
| ----------------------------- |--------------------|--------------------------|-------------------------------------------
| \Acme\Log\Writer\File_Writer  | Acme\Log\Writer    | ./acme-log-writer/lib/   | ./acme-log-writer/lib/File_Writer.php
| \Aura\Web\Response\Status     | Aura\Web           | /path/to/aura-web/src/   | /path/to/aura-web/src/Response/Status.php
| \Symfony\Core\Request         | Symfony\Core       | ./vendor/Symfony/Core/   | ./vendor/Symfony/Core/Request.php
| \Zend\Acl                     | Zend               | /usr/includes/Zend/      | /usr/includes/Zend/Acl.php

For example implementations of autoloaders conforming to the specification,
please see the [examples file][]. Example implementations MUST NOT be regarded
as part of the specification and MAY change at any time.

[autoloading]: http://php.net/autoload
[PSR-0]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md
[examples file]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-4-autoloader-examples.md



## 4. PSR-0 Autoloader

===================================================================================================================
```
https://viblo.asia/p/coding-convention-doi-voi-mot-project-php-ORNZqNPrl0n
https://viblo.asia/p/coding-convention-psr-va-coding-standard-in-framgia-djeZ1amQZWz
```

Chuẩn PSR-0 là một chuẩn cho autoloading classes. Tuy nhiên từ tháng 10/2014 PSR-0 đã được đề suất không sử dụng nữa và PSR-4 được đề xuất thay thế. Tuy nhiên, chúng ta cũng nên tìm hiểu xem PSR-0 có gì đặc biệt, biết đâu vẫn có lúc sử dụng thì sao.

Một namespace và class chuẩn phải tuân theo cấu trúc: <Vendor Name>(<Namespace>)<Class Name>
Mỗi namespace có namespace gốc <Vendor Name>
Một namespace có thể chứa bao nhiêu namespace con (sub-namespace) cũng được.
Mỗi kí tự _ trong tên class sẽ được chuyển đổi thành DIRECTORY_SEPARATOR . Kí tự _ không có ý nghĩa đặc biệt gì trong namespace.
Khi được tải từ file hệ thống, namespace và class sẽ có chứa hậu tố .php.
Đối với vendor names, namespace và class names, có thể kết hợp giữa chữ hoa và chữ thường.