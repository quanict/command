# PHP coding conventions

Tuân theo chuẩn PSR (PHP Standards Recommendation) của nhóm FIG

https://www.php-fig.org/psr/
https://github.com/php-fig/fig-standards/tree/master/accepted

## PSR-1: Basic Coding Standard
```
https://www.php-fig.org/psr/psr-1/
```
### 1.1 Files

#### 1.1.1 PHP tags

Code phải được viết trong cặp thẻ <?php ?> và nên sử dụng cặp thẻ ngắn <?= ?> thay cho echo. Không sử dụng các thẻ khác

#### 1.1.2 Character Encoding
Code chỉ được sử dụng UTF-8 không có BOM (BOM - Byte Order Mark là các chuỗi EF,BB,BF ở đầu file cho phép phần mềm biết đây là 1 file UTF-8).

#### 1.1.3 Side Effects
– Mỗi một file PHP chỉ nên làm 1 nhiệm vụ duy nhất ( chứa một class, chứa functions, hoặc chứa constants ... ), tránh chồng chéo (gọi là side effect).

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
 
– Tên class phải viết theo quy tắc StudlyCaps.


Code viết cho PHP 5.2.x và phiên bản cũ hơn  phải sử dụng quy ước pseudo-namespacing ( sử dụng `Vendor_` trước trên class )

~~~php
<?php
// PHP 5.2.x and earlier:
class Vendor_Model_Foo
{
}
~~~

### 1.3 Class Constants, Properties, and Methods

#### 1.3.1 Hằng Số
– Các hẳng số phải viết hoa tất cả các chữ, cách nhau bằng dấu gạch chân.

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

Tuân thủ theo một quy tắc nhất định, không nên sử dụng nhiều quy ước.

~~~
Quy ước dùng quy tắc camelCase để đặt tên thuộc tính.
~~~

#### 1.3.3 Methods
Tên phương thức viết theo quy tắc camelCase.

## PSR-2: Coding Style Guide

### 2.1. Basic Coding Standard
- Code phải tuân thủ tất cả chuẩn [PSR-1] & [PSR-0].

### 2.2. Files
- Các file phải sử dụng Unix LF (linefeed) để kết thúc dòng.
- Các file PHP phải kết thúc bằng một dòng trắng.
- Thẻ đóng `?>` không sử dụng ở file chỉ chứ code PHP

### 2.3. Lines
- Trên 1 dòng không vượt quá 120 kí tự, tốt nhất nên nhỏ hơn hoặc bằng 80 kí tự.
- Không nên có kí tự trắng ở cuối dòng code.
- Có thể sử dụng dòng trắng để chia tách các khối để cho view code dễ dàng hơn.
- Không được sử dụng nhiều khai báo, toán tử trên cùng một dòng

### 2.4. Cách đầu dòng
- Sử dụng 4 khoảng trắng(spaces) để thụt dòng, tuyệt đối không dùng tab (bạn có thể khai báo trong công cụ lập trình để khi ấn tab nó tương đương với việc thụt vào 4 spaces).

### 2.5. Keywords and True/False/Null

- Những PHP [keywords] phải viết chữ thường.
- Những hằng số PHP `true`, `false`, và `null` phải viết thường.

[keywords]: http://php.net/manual/en/reserved.keywords.php

## 3. Namespace and Use Declarations

- Phải có 1 dòng trắng sau khi khai báo namespace và phải có 1 dòng trắng sau các khai báo use.
- Tất cả những khai báo `use` phải viết sau khai báo `namespace`
- Phải sử dụng từ khóa `use` cho mỗi khai báo
- Phải sủ dụng một dòng trắng sau mỗi khối khai báo `use`

For example:

~~~php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

// ... additional PHP code ...

~~~

## 4. Classes, Properties, and Methods

The term "class" refers to all classes, interfaces, and traits.

### 4.1. Extends and Implements

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

Danh sách các `implements` phải được tách ra thành nhiều dòng, mỗi một dòng chứa một khai báo riêng biệt.

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

### 4.2. Properties

Visibility MUST be declared on all properties.

The `var` keyword MUST NOT be used to declare a property.

There MUST NOT be more than one property declared per statement.

Property names SHOULD NOT be prefixed with a single underscore to indicate
protected or private visibility.

A property declaration looks like the following.

~~~php
<?php
namespace Vendor\Package;

class ClassName
{
    public $foo = null;
}
~~~

### 4.3. Methods

Visibility MUST be declared on all methods.

Method names SHOULD NOT be prefixed with a single underscore to indicate
protected or private visibility.

Method names MUST NOT be declared with a space after the method name. The
opening brace MUST go on its own line, and the closing brace MUST go on the
next line following the body. There MUST NOT be a space after the opening
parenthesis, and there MUST NOT be a space before the closing parenthesis.

A method declaration looks like the following. Note the placement of
parentheses, commas, spaces, and braces:

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

### 4.4. Method Arguments

In the argument list, there MUST NOT be a space before each comma, and there
MUST be one space after each comma.

Method arguments with default values MUST go at the end of the argument
list.

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

Argument lists MAY be split across multiple lines, where each subsequent line
is indented once. When doing so, the first item in the list MUST be on the
next line, and there MUST be only one argument per line.

When the argument list is split across multiple lines, the closing parenthesis
and opening brace MUST be placed together on their own line with one space
between them.

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

### 4.5. `abstract`, `final`, and `static`

When present, the `abstract` and `final` declarations MUST precede the
visibility declaration.

When present, the `static` declaration MUST come after the visibility
declaration.

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

### 4.6. Method and Function Calls

When making a method or function call, there MUST NOT be a space between the
method or function name and the opening parenthesis, there MUST NOT be a space
after the opening parenthesis, and there MUST NOT be a space before the
closing parenthesis. In the argument list, there MUST NOT be a space before
each comma, and there MUST be one space after each comma.

~~~php
<?php
bar();
$foo->bar($arg1);
Foo::bar($arg2, $arg3);
~~~

Argument lists MAY be split across multiple lines, where each subsequent line
is indented once. When doing so, the first item in the list MUST be on the
next line, and there MUST be only one argument per line.

~~~php
<?php
$foo->bar(
    $longArgument,
    $longerArgument,
    $muchLongerArgument
);
~~~

## 5. Control Structures

The general style rules for control structures are as follows:

- There MUST be one space after the control structure keyword
- There MUST NOT be a space after the opening parenthesis
- There MUST NOT be a space before the closing parenthesis
- There MUST be one space between the closing parenthesis and the opening
  brace
- The structure body MUST be indented once
- The closing brace MUST be on the next line after the body

The body of each structure MUST be enclosed by braces. This standardizes how
the structures look, and reduces the likelihood of introducing errors as new
lines get added to the body.

### 5.1. `if`, `elseif`, `else`

An `if` structure looks like the following. Note the placement of parentheses,
spaces, and braces; and that `else` and `elseif` are on the same line as the
closing brace from the earlier body.

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

The keyword `elseif` SHOULD be used instead of `else if` so that all control
keywords look like single words.

### 5.2. `switch`, `case`

A `switch` structure looks like the following. Note the placement of
parentheses, spaces, and braces. The `case` statement MUST be indented once
from `switch`, and the `break` keyword (or other terminating keyword) MUST be
indented at the same level as the `case` body. There MUST be a comment such as
`// no break` when fall-through is intentional in a non-empty `case` body.

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

### 5.3. `while`, `do while`

A `while` statement looks like the following. Note the placement of
parentheses, spaces, and braces.

~~~php
<?php
while ($expr) {
    // structure body
}
~~~

Similarly, a `do while` statement looks like the following. Note the placement
of parentheses, spaces, and braces.

~~~php
<?php
do {
    // structure body;
} while ($expr);
~~~

### 5.4. `for`

A `for` statement looks like the following. Note the placement of parentheses,
spaces, and braces.

~~~php
<?php
for ($i = 0; $i < 10; $i++) {
    // for body
}
~~~

### 5.5. `foreach`

A `foreach` statement looks like the following. Note the placement of
parentheses, spaces, and braces.

~~~php
<?php
foreach ($iterable as $key => $value) {
    // foreach body
}
~~~

### 5.6. `try`, `catch`

A `try catch` block looks like the following. Note the placement of
parentheses, spaces, and braces.

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

## 6. Closures

Closures MUST be declared with a space after the `function` keyword, and a
space before and after the `use` keyword.

The opening brace MUST go on the same line, and the closing brace MUST go on
the next line following the body.

There MUST NOT be a space after the opening parenthesis of the argument list
or variable list, and there MUST NOT be a space before the closing parenthesis
of the argument list or variable list.

In the argument list and variable list, there MUST NOT be a space before each
comma, and there MUST be one space after each comma.

Closure arguments with default values MUST go at the end of the argument
list.

A closure declaration looks like the following. Note the placement of
parentheses, commas, spaces, and braces:

~~~php
<?php
$closureWithArgs = function ($arg1, $arg2) {
    // body
};

$closureWithArgsAndVars = function ($arg1, $arg2) use ($var1, $var2) {
    // body
};
~~~

Argument lists and variable lists MAY be split across multiple lines, where
each subsequent line is indented once. When doing so, the first item in the
list MUST be on the next line, and there MUST be only one argument or variable
per line.

When the ending list (whether of arguments or variables) is split across
multiple lines, the closing parenthesis and opening brace MUST be placed
together on their own line with one space between them.

The following are examples of closures with and without argument lists and
variable lists split across multiple lines.

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

Note that the formatting rules also apply when the closure is used directly
in a function or method call as an argument.

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

## 7. Conclusion

There are many elements of style and practice intentionally omitted by this
guide. These include but are not limited to:

- Declaration of global variables and global constants

- Declaration of functions

- Operators and assignment

- Inter-line alignment

- Comments and documentation blocks

- Class name prefixes and suffixes

- Best practices

Future recommendations MAY revise and extend this guide to address those or
other elements of style and practice.


