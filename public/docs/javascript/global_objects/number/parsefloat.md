Number.parseFloat()
===================

The `Number.parseFloat()` method parses an argument and returns a floating point number. If a number cannot be parsed from the argument, it returns [`NaN`](../nan).

Syntax
------

    Number.parseFloat(string)

### Parameters

`string`  
The value to parse. If this argument is not a string, then it is converted to one using the `ToString` abstract operation. Leading [whitespace](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace) in this argument is ignored.

### Return value

A floating point number parsed from the given `string`.

Or [`NaN`](../nan) when the first non-whitespace character cannot be converted to a number.

Polyfill
--------

    if (Number.parseFloat === undefined) {
      Number.parseFloat = parseFloat;
    }

Examples
--------

### Number.parseFloat vs parseFloat

This method has the same functionality as the global [`parseFloat()`](../parsefloat) function:

    Number.parseFloat === parseFloat; // true

This method is also part of ECMAScript 2015. (Its purpose is modularization of globals.)

See [`parseFloat()`](../parsefloat) for more detail and examples.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-number.parsefloat">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-number.parsefloat</span></a></td></tr></tbody></table>

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

`parseFloat`

34

12

25

No

21

9

≤37

34

25

21

9

2.0

See also
--------

-   [`Number`](../number)  
    The object this method belongs to.

-   The global [`parseFloat()`](../parsefloat) method.

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/parseFloat" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/parseFloat</a>
