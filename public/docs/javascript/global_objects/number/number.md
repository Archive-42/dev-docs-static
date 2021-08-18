Number() constructor
====================

The `Number()` creates a [`Number`](../number) object.

Syntax
------

    new Number(value)

### Parameters

`value`  
The numeric value of the object being created.

Examples
--------

### Creating Number objects

    const a = new Number('123'); // a === 123 is false
    const b = Number('123');     // b === 123 is true
    a instanceof Number;         // is true
    b instanceof Number;         // is false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-number-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-number-constructor</span></a></td></tr></tbody></table>

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

`Number`

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

-   [`NaN`](../nan)
-   The [`Math`](../math) global object
-   Integers with arbitrary precision: [`BigInt`](../bigint)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/Number" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/Number</a>
