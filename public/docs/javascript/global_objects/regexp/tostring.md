RegExp.prototype.toString()
===========================

The `toString()` method returns a string representing the regular expression.

Syntax
------

    toString()

### Return value

A string representing the given object.

Description
-----------

The [`RegExp`](../regexp) object overrides the `toString()` method of the [`Object`](../object) object; it does not inherit [`Object.prototype.toString()`](../object/tostring). For [`RegExp`](../regexp) objects, the `toString()` method returns a string representation of the regular expression.

Examples
--------

### Using toString()

The following example displays the string value of a [`RegExp`](../regexp) object:

    var myExp = new RegExp('a+b+c');
    console.log(myExp.toString());  // logs '/a+b+c/'

    var foo = new RegExp('bar', 'g');
    console.log(foo.toString());    // logs '/bar/g'

### Empty regular expressions and escaping

Starting with ECMAScript 5, an empty regular expression returns the string "/(?:)/" and line terminators such as "\\n" are escaped:

    new RegExp().toString(); // "/(?:)/"

    new RegExp('\n').toString() === '/\n/';  // true, prior to ES5
    new RegExp('\n').toString() === '/\\n/'; // true, starting with ES5

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-regexp.prototype.tostring">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-regexp.prototype.tostring</span></a></td></tr></tbody></table>

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

`toString`

1

12

1

4

5

1

1

18

4

10.1

1

1.0

`escaping`

73

12

38

9

60

6

73

73

38

52

6

No

See also
--------

-   [`Object.prototype.toString()`](../object/tostring)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/toString</a>
