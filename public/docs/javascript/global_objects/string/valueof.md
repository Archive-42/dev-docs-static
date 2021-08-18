String.prototype.valueOf()
==========================

The `valueOf()` method returns the primitive value of a [`String`](../string) object.

Syntax
------

    valueOf()

### Return value

A string representing the primitive value of a given [`String`](../string) object.

Description
-----------

The `valueOf()` method of [`String`](../string) returns the primitive value of a [`String`](../string) object as a string data type. This value is equivalent to [`String.prototype.toString()`](tostring).

This method is usually called internally by JavaScript and not explicitly in code.

Examples
--------

### Using `valueOf()`

    var x = new String('Hello world');
    console.log(x.valueOf()); // Displays 'Hello world'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-string.prototype.valueof">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-string.prototype.valueof</span></a></td></tr></tbody></table>

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

`valueOf`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

See also
--------

-   [`String.prototype.toString()`](tostring)
-   [`Object.prototype.valueOf()`](../object/valueof)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/valueOf" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/valueOf</a>
