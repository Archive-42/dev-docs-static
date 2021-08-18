String.prototype.toString()
===========================

The `toString()` method returns a string representing the specified object.

Syntax
------

    toString()

### Return value

A string representing the calling object.

Description
-----------

The [`String`](../string) object overrides the `toString()` method of the [`Object`](../object) object; it does not inherit [`Object.prototype.toString()`](../object/tostring). For [`String`](../string) objects, the `toString()` method returns a string representation of the object and is the same as the [`String.prototype.valueOf()`](valueof) method.

Examples
--------

### Using `toString()`

The following example displays the string value of a [`String`](../string) object:

    var x = new String('Hello world');

    console.log(x.toString()); // logs 'Hello world'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-string.prototype.tostring">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-string.prototype.tostring</span></a></td></tr></tbody></table>

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

3

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

-   [`Object.prototype.toSource()`](../object/tosource)
-   [`String.prototype.valueOf()`](valueof)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toString</a>
