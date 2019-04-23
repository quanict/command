# PHP coding conventions

Tuân theo chuẩn PSR (PHP Standards Recommendation) của nhóm FIG

```links
https://www.php-fig.org/psr/
https://github.com/php-fig/fig-standards/tree/master/accepted
```

## 1. PSR-1 Basic Coding Standard

===================================================================================================================

```links
https://www.php-fig.org/psr/psr-1/
```

### 1.1 Files

#### 1.1.1 PHP tags

- Code PHẢI được viết trong cặp thẻ `<?php ?>` và nên sử dụng cặp thẻ ngắn `<?= ?>` thay cho echo. Không sử dụng các thẻ khác

#### 1.1.2 Character Encoding

- Code CHỈ ĐƯỢC sử dụng UTF-8 KHÔNG ĐƯỢC DÙNG [BOM].

[BOM] : BOM - Byte Order Mark là các chuỗi EF,BB,BF ở đầu file cho phép phần mềm biết đây là 1 file UTF-8

#### 1.1.3 Side Effects

- Mỗi một file `PHP` CHỈ ĐƯỢC nên làm 1 nhiệm vụ duy nhất ( chứa một class, chứa functions, hoặc chứa constants ... ), tránh chồng chéo (gọi là side effect).

### 1.2 Namespace and Class Names

- [Namespace] PHẢI tuân theo chuẩn PSR “autoloading” (PSR-0, PSR-4).
- Tên của class PHẢI trùng với tên file chứa class

~~~php
<?php
// PHP 5.3 and later:
namespace Vendor\Model;

class Foo
{
}
~~~

- Tên class PHẢI viết theo quy tắc [StudlyCaps].
- Code viết cho PHP 5.2.x và phiên bản cũ hơn  PHẢI sử dụng quy ước [pseudo-namespacing] ( sử dụng `Vendor_` trước trên class )

~~~php
<?php
// PHP 5.2.x and earlier:
class Vendor_Model_Foo
{
}
~~~

### 1.3 Class Constants, Properties, and Methods

#### 1.3.1 Hằng Số

- Các hẳng số PHẢI viết hoa, cách nhau bằng dấu gạch chân.

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

- Tuân NÊN thủ theo một quy tắc nhất định, KHÔNG NÊN sử dụng nhiều quy ước.

~~~note
Quy ước dùng quy tắc [camelCase] để đặt tên thuộc tính.
~~~

#### 1.3.3 Methods

- Tên phương thức PHẢI viết theo quy tắc [camelCase].

## 2. PSR-2: Coding Style Guide

===================================================================================================================

```link
https://www.php-fig.org/psr/psr-2/
```

### 2.1 General

- Code PHẢI tuân theo PSR [PSR-1].
- Code PHẢI sử dụng 4 [space] để thụt lề, không dùng `tab`.
- KHÔNG CÓ giới hạn bắt buộc chiều dài cố định một dòng, giới hạn tối đa KHÔNG ĐƯỢC quá 120 ký tự, TỐT NHẤT nên nhỏ hơn hoặc bằng 80 kí tự.
- PHẢI CÓ một dòng trắng sau khai báo [namespace], và PHẢI có một dòng trắng sau mỗi khối khai báo.
- Ký tự mở `class`, `method` PHẢI ở một dòng riêng biệt, và ký tự đóng PHẢI ở một dòng riêng biệt.
- Tất cả các `method` PHẢI được khai báo đặc điểm  `Visibility`, các thuộc tính `abstract` và `final` PHẢI được khai báo trước `Visibility`. Thuộc tính `static` PHẢI được khai báo sau `Visibility`.
- Từ khóa của một cấu trúc PHẢI có một [space] phía sau. Nhưng phương thức và gọi [function] thì KHÔNG CÓ.
- Ký tự mở một cấu trúc '{' PHẢI được viết cùng dòng, và ký tự đóng '}' PHẢI được viết ở một dòng riêng.
- Ký tự bắt đầu khai báo tham số cho một cấu trúc KHÔNG ĐƯỢC có ký tự [space] phía sau, và ký tự đóng KHÔNG ĐƯỢC có [space] phía trước.

#### 2.1.1 Basic Coding Standard

- Code PHẢI tuân thủ tất cả chuẩn [PSR-1].

#### 2.1.2 Files

- Các file PHẢI sử dụng [Unix LF] (linefeed) để kết thúc dòng.
- Các file `PHP` PHẢI kết thúc bằng một dòng trắng.
- Thẻ đóng `?>` KHÔNG ĐƯỢC sử dụng ở file chỉ chứa `code PHP`

#### 2.1.3 Lines

- Trên 1 dòng KHÔNG ĐƯỢC vượt quá 120 kí tự, TỐT NHẤT nên nhỏ hơn hoặc bằng 80 kí tự.
- KHÔNG ĐƯỢC có kí tự trắng ở cuối dòng code.
- CÓ THỂ sử dụng dòng trắng để chia tách các khối để cho view code dễ dàng hơn.
- KHÔNG ĐƯỢC sử dụng nhiều khai báo, toán tử trên cùng một dòng

#### 2.1.4 Cách đầu dòng

- PHẢI sử dụng 4 khoảng trắng(spaces) để thụt dòng, TUYỆT ĐỐI không dùng tab (bạn có thể khai báo trong công cụ lập trình để khi ấn tab nó tương đương với việc thụt vào 4 spaces).

#### 2.1.5 Keywords and True/False/Null

- Những PHP [keywords] PHẢI viết chữ thường.
- Những hằng số  PHP `true`, `false`, và `null` PHẢI viết thường.

[keywords]: http://php.net/manual/en/reserved.keywords.php

### 2.2 Namespace and Use Declarations

- PHẢI có 1 dòng trắng sau khi khai báo [namespace] và PHẢI có 1 dòng trắng sau các khai báo `use`.
- Tất cả những khai báo `use` PHẢI viết sau khai báo `namespace`
- PHẢI sử dụng từ khóa `use` cho mỗi khai báo
- PHẢI sủ dụng một dòng trắng sau mỗi khối khai báo `use`

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

- Từ khóa `extends` và `implements` PHẢI được sử dụng trên cùng một dòng với [tên class].
- Khai báo thẻ mở và thẻ đóng một class PHẢI ở một dòng riêng biệt.

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

- Danh sách các `implements` PHẢI được tách ra thành nhiều dòng, mỗi một dòng chứa một khai báo riêng biệt.

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

- Tất cả các thuộc tính PHẢI được khai báo đặc điểm `Visibility`
- KHÔNG ĐƯỢC sử dụng từ khóa `var` khi khai báo [property]
- KHÔNG ĐƯỢC sử dụng nhiều hơn một [property] cho mỗi khai báo.
- Tên của [property] KHÔNG NÊN dùng gạch dưới để khai báo đặc tính [protected] hay [private]

~~~php
<?php
namespace Vendor\Package;

class ClassName
{
    public $foo = null;
}
~~~

#### 2.3.3 Methods

- Tất cả các phương thức PHẢI được khai báo đặc điểm `Visibility`
- Tên của [Method] KHÔNG NÊN dùng gạch dưới để khai báo đặc tính [protected] hay [private]
- Tên của [Method] KHÔNG ĐƯỢC có ký tự [space] phía sau khai báo. Ký tự mở [{] và đóng [}] PHẢI được viết ở một dòng riêng biệt, và KHÔNG ĐƯỢC có ký tự [space] sau.

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

- Khi dùng nhiều biến cho [method], KHÔNG ĐƯỢC dùng [space] trước mỗi dấu phẩy, và PHẢI có một [space] sau môi dấu phẩy
- Biến cho [method] có giá trị mặc định thì PHẢI khai báo sau cùng khi khai báo [method]

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

- Biến cho [method] CÓ THỂ khai báo thành nhiều dòng, mỗi dòng CHỈ ĐƯỢC khai báo một biến.
- Khi khai báo biến cho [method] trên nhiều dòng, thì ký tự đóng argument [(] và mở method [{] PHẢI được phân tách bằng một [space]

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

- Khi khai báo các đặc tính `abstract` và `final`  thì PHẢI dùng trước các khai báo `public` và `protected`
- Khi khai báo `static` thì PHẢI khai báo sau các khai báo `public` và `protected`

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

- Khi khởi tạo một [method] hay gọi [function], KHÔNG ĐƯỢC có ký tự [space] ở giữa [method], tên [function] và ký tự mở [(], KHÔNG ĐƯỢC có [space] phía trước ký tự đóng [)]
- Trong danh sách các biến KHÔNG ĐƯỢC có [space] trước dấu phẩy, và PHẢI có [space] phía sau dấy phẩy

~~~php
<?php
bar();
$foo->bar($arg1);
Foo::bar($arg2, $arg3);
~~~

- Các biến CÓ THỂ  phân tách thành nhiều dòng, lúc này, mỗi biến PHẢI được trình bày ở một dòng riêng biệt.

~~~php
<?php
$foo->bar(
    $longArgument,
    $longerArgument,
    $muchLongerArgument
);
~~~

### 2.4 Control Structures

- PHẢI có [space] sau mỗi toán tử chuyển hướng
- PHẢI có một [space] phía sau từ khóa của khối cấu trúc
- KHÔNG ĐƯỢC có [space] sau thẻ mở toán tử  chuyển hướng
- KHÔNG ĐƯỢC có [space] phía sau ky tự mở [{], và phía trước ký tự đóng [}]
- PHẢI có một [space] giữa thẻ đóng [)] và thẻ mở [{]
- Nội dung của [structure] PHẢI được cách lề  hơn so với tên
- Ký tự đóng PHẢI được viết ở dòng tiếp theo so với nội dung, nằm ở dòng mới riêng biệt.
- Nội dung của [structure] PHẢI được bao đóng bởi ký tự ngoặc [{] và [}], điều này giúp cho chuẩn hóa cách tổ  chức code cho [structure] và hạn chế lỗi khi thêm code vào [structure]

#### 2.4.1. `if`, `elseif`, `else`

- Chú ý toán tử  `else` và `elseif` PHẢI được viết cùng một dòng với ký tự đóng điều kiện trước.
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

- KHÔNG NÊN dùng toán tử  `else if` , nên thay bằng toán tử  `elseif`.

#### 2.4.2. `switch`, `case`

- Toán tử  `case` PHẢI được sử dụng trong `switch`, và toán tử  `break` phải được đặt ở level trên cùng trong nội dụng của `case`. BẮT BUỘC PHẢI comment ở `case` không bình thường, ví dụ `// no break` ở ví dụ sau.
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

### 2.5. Closures

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

### 2.6. Ví dụ Coding Style

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

## 3. PSR-3: Logger Interface

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
~~~

## 4. PSR-4 Autoloader

===================================================================================================================

```link
https://www.php-fig.org/psr/psr-4/
```

### 4.1. Tổng quan

PSR đưa ra các quy ước cho [autoloading][] classes trong files. Nó bao gồm cả những quy tắc [PSR-0], và gồm những quy tắc đặt files.

### 4.2. Mô tả

#### 4.2.1. Khái niệm "class" để chỉ  các lớp, interfaces, traits, và cả các cấu trúc tương tự khác.

#### 4.2.2. Khai báo đầy đủ một `class` có dạng sau

~~~php
\<NamespaceName>(\<SubNamespaceNames>)*\<ClassName>
~~~

- Khai báo đây đủ PHẢI có [namespace] của mức cá nhất, có thể hiểu là [vendor namespace]
- Tên xác định đầy đủ PHẢI có một namespace gốc.
- Khai báo đầy đủ thể CÓ THỂ có một hoặc nhiều [namespace] con
- Khai báo đầy đủ PHẢI CÓ một 'tên lớp kết thúc' (terminating class name)
- Tất cả các lớp PHẢI được tham chiếu có phân biệt chữ hoa và chữ thường

#### 4.2.3. Khi `load` một file, phải tương ứng với một 'fully qualified class name'.

#### 4.2.3. Điều kiện khi `loading` class đầy đủ

    - Một chuỗi liên tục, có thể có một hoặc nhiều [namespace], không có dấu phân tách [namespace], trong [namespace prefix] phải có ít nhất một "base directory".
    - Các [namespace] con, ở phái sau "namespace prefix" phải tương ứng với một thư mục nằm trong "base directory". Tên thư mục con PHẢI trùng với [namespace] con.
    - Tên của [terminating class] PHẢI tương ứng với trên file `.php`

#### 4.2.4. Sử dụng [Autoloader] không được trả về lỗi, không được đưa ra bất kỳ lỗi nào, không trả về giá trị

### 4.3. Ví dụ

| Fully Qualified Class Name    | Namespace Prefix   | Base Directory           | Resulting File Path
| ----------------------------- |--------------------|--------------------------|-------------------------------------------
| \Acme\Log\Writer\File_Writer  | Acme\Log\Writer    | ./acme-log-writer/lib/   | ./acme-log-writer/lib/File_Writer.php
| \Aura\Web\Response\Status     | Aura\Web           | /path/to/aura-web/src/   | /path/to/aura-web/src/Response/Status.php
| \Symfony\Core\Request         | Symfony\Core       | ./vendor/Symfony/Core/   | ./vendor/Symfony/Core/Request.php
| \Zend\Acl                     | Zend               | /usr/includes/Zend/      | /usr/includes/Zend/Acl.php

[autoloading]: http://php.net/autoload
[PSR-0]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md
[examples file]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-4-autoloader-examples.md

## 5. Quy ước khác

- Tối đa mỗi hàm, [method] KHÔNG NÊN quá 15 dòng.
- Tách các nghiệp vụ thành các hàm riêng biệt
- Tương tự với các object, khi đủ lớn, nên tác thành các [method]
- Số lượng rẽ nhánh trong các `switch`, `if`, `else` KHÔNG NÊN quá 4
- Hạn chế tối đa sử dụng các điều kiện rẽ nhánh
- Tham số của [class] NÊN là 4
- NÊN xóa những đoạn [code chết]
- PHẢI comment mô tả cho class, method, function.
- PHẢI đặt tên biến, tham số, hàm, class liên quan đến mục đích sử dụng
- KHÔNG NÊN đặt trên biến, tham số, hàm, class quá dài
- Tên method, phải được bắt đầu bằng một động từ 'GET', 'POST, 'UPDATE', 'PUT' ...


## 6. Tài liệu

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