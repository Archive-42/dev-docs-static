String.prototype.concat()
=========================

The `concat()` method concatenates the string arguments to the calling string and returns a new string.

Syntax
------

    concat(str1)
    concat(str1, str2)
    concat(str1, str2, ... , strN)

### Parameters

`strN`  
One or more strings to concatenate to `str`.

### Return value

A new string containing the combined text of the strings provided.

Description
-----------

The `concat()` function concatenates the string arguments to the calling string and returns a new string. Changes to the original string or the returned string don't affect the other.

If the arguments are not of the type string, they are converted to string values before concatenating.

Performance
-----------

It is strongly recommended that the [assignment operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#assignment_operators) (`+`, `+=`) are used instead of the `concat()` method.

Examples
--------

### Using concat()

The following example combines strings into a new string.

    let hello = 'Hello, '
    console.log(hello.concat('Kevin', '. Have a nice day.'))
    // Hello, Kevin. Have a nice day.

    let greetList = ['Hello', ' ', 'Venkat', '!']
    "".concat(...greetList)  // "Hello Venkat!"

    "".concat({})    // [object Object]
    "".concat([])    // ""
    "".concat(null)  // "null"
    "".concat(true)  // "true"
    "".concat(4, 5)  // "45"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-string.prototype.concat">ECMAScript (ECMA-262)<br />
<span class="small">The definition of 'String.prototype.concat' in that specification.</span></a></td></tr></tbody></table>

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`concat`

1

12

1

4

4

1

1

18

4

10.1

1

1.0

See also
--------

-   [`Array.prototype.concat()`](../array/concat)
-   [Assignment operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#assignment_operators)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/concat" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/concat</a>
