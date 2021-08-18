BigInt.prototype.valueOf()
==========================

The `valueOf()` method returns the wrapped primitive value of a [`BigInt`](../bigint) object.

Syntax
------

    bigIntObj.valueOf()

### Return value

A BigInt representing the primitive value of the specified [`BigInt`](../bigint) object.

Examples
--------

### Using `valueOf`

    typeof Object(1n); // object
    typeof Object(1n).valueOf(); // bigint

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-bigint.prototype.valueof">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-bigint.prototype.valueof</span></a></td></tr></tbody></table>

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

67

79

68

No

54

14

67

67

68

48

14

9.0

See also
--------

-   [`BigInt.prototype.toString()`](tostring)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt/valueOf" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt/valueOf</a>
