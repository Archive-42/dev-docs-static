Number.prototype.toString()
===========================

The `toString()` method returns a string representing the specified [`Number`](../number) object.

Syntax
------

    toString()
    toString(radix)

### Parameters

 `radix` <span class="badge inline optional">Optional</span>   
An integer in the range `2` through `36` specifying the base to use for representing numeric values.

### Return value

A string representing the specified [`Number`](../number) object.

### Exceptions

[`RangeError`](../rangeerror)  
If `toString()` is given a `radix` less than `2` or greater than `36`, a [`RangeError`](../rangeerror) is thrown.

Description
-----------

The [`Number`](../number) object overrides the `toString()` method of the [`Object`](../object) object. (It does *not* inherit [`Object.prototype.toString()`](../object/tostring)). For [`Number`](../number) objects, the `toString()` method returns a string representation of the object in the specified radix.

The `toString()` method parses its first argument, and attempts to return a string representation in the specified `radix` (base). For radices above `10`, the letters of the alphabet indicate numerals greater than 9. For example, for hexadecimal numbers (base 16), `a` through `f` are used.

If the `radix` is not specified, the preferred radix is assumed to be `10`.

If the `numObj` is negative, the sign is preserved. This is the case even if the radix is `2`; the string returned is the positive binary representation of the `numObj` preceded by a `-` sign, **not** the two's complement of the `numObj`.

If the `numObj` is not a whole number, the 'dot' sign is used to separate the decimal places.

Examples
--------

### Using toString

    let count = 10

    console.log(count.toString())    // displays '10'
    console.log((17).toString())     // displays '17'
    console.log((17.2).toString())   // displays '17.2'

    let x = 6

    console.log(x.toString(2))       // displays '110'
    console.log((254).toString(16))  // displays 'fe'

    console.log((-10).toString(2))   // displays '-1010'
    console.log((-0xff).toString(2)) // displays '-11111111'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-number.prototype.tostring">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-number.prototype.tostring</span></a></td></tr></tbody></table>

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

-   [`Number.prototype.toFixed()`](tofixed)
-   [`Number.prototype.toExponential()`](toexponential)
-   [`Number.prototype.toPrecision()`](toprecision)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toString</a>
