Number.prototype.valueOf()
==========================

The `valueOf()` method returns the wrapped primitive value of a [`Number`](../number) object.

Syntax
------

    valueOf()

### Return value

A number representing the primitive value of the specified [`Number`](../number) object.

Description
-----------

This method is usually called internally by JavaScript and not explicitly in web code.

Examples
--------

### Using valueOf

    let numObj = new Number(10)
    console.log(typeof numObj)  // object

    let num = numObj.valueOf()
    console.log(num)            // 10
    console.log(typeof num)     // number

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-number.prototype.valueof">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-number.prototype.valueof</span></a></td></tr></tbody></table>

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

-   [`Number.prototype.toSource()`](tosource)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/valueOf" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/valueOf</a>
