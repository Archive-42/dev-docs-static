BigInt.prototype.toString()
===========================

The `toString()` method returns a string representing the specified [`BigInt`](../bigint) object. The trailing "n" is not part of the string.

Syntax
------

    toString()
    toString(radix)

### Parameters

 `radix`<span class="badge inline optional">Optional</span>   
Optional. An integer in the range 2 through 36 specifying the base to use for representing numeric values.

### Return value

A string representing the specified [`BigInt`](../bigint) object.

### Exceptions

[`RangeError`](../rangeerror)  
If `toString()` is given a radix less than 2 or greater than 36, a [`RangeError`](../rangeerror) is thrown.

Description
-----------

The [`BigInt`](../bigint) object overrides the `toString()` method of the [`Object`](../object) object; it does not inherit [`Object.prototype.toString()`](../object/tostring). For [`BigInt`](../bigint) objects, the `toString()` method returns a string representation of the object in the specified radix.

The `toString()` method parses its first argument, and attempts to return a string representation in the specified radix (base). For radixes above 10, the letters of the alphabet indicate numerals greater than 9. For example, for hexadecimal numbers (base 16) `a` through `f` are used.

If the `radix` is not specified, the preferred radix is assumed to be 10.

If the `bigIntObj` is negative, the sign is preserved. This is the case even if the radix is 2; the string returned is the positive binary representation of the `bigIntObj` preceded by a `-` sign, **not** the two's complement of the `bigIntObj`.

Examples
--------

### Using `toString`

    17n.toString();      // '17'
    66n.toString(2);     // '1000010'
    254n.toString(16);   // 'fe'
    -10n.toString(2);    // -1010'
    -0xffn.toString(2);  // '-11111111'

### Negative-zero `BigInt`

There is no negative-zero `BigInt` as there are no negative zeros in integers. `-0.0` is an IEEE floating-point concept that only appears in the JavaScript [`Number`](../number) type.

    (-0n).toString();      // '0'
    BigInt(-0).toString(); // '0'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-bigint.prototype.tostring">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-bigint.prototype.tostring</span></a></td></tr></tbody></table>

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

-   [`BigInt.prototype.toLocaleString()`](tolocalestring)
-   [`BigInt.prototype.valueOf()`](valueof)
-   [`Number.prototype.toString()`](../number/tostring)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt/toString</a>
