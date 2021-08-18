isFinite()
==========

The global `isFinite()` function determines whether the passed value is a finite number. If needed, the parameter is first converted to a number.

Syntax
------

    isFinite(testValue)

### Parameters

`testValue`  
The value to be tested for finiteness.

### Return value

`false` if the argument is (or will be coerced to) positive or negative [`Infinity`](infinity) or [`NaN`](nan) or [`undefined`](undefined); otherwise, `true`.

Description
-----------

`isFinite` is a function property of the global object.

You can use this function to determine whether a number is a finite number. The `isFinite` function examines the number in its argument. If the argument is `NaN`, positive infinity, or negative infinity, this method returns `false`; otherwise, it returns `true`.

Examples
--------

### Using isFinite

    isFinite(Infinity);  // false
    isFinite(NaN);       // false
    isFinite(-Infinity); // false

    isFinite(0);         // true
    isFinite(2e64);      // true
    isFinite(910);       // true

    isFinite(null);      // true, would've been false with the
                         // more robust Number.isFinite(null)

    isFinite('0');       // true, would've been false with the
                         // more robust Number.isFinite("0")

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-isfinite-number">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-isfinite-number</span></a></td></tr></tbody></table>

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

`isFinite`

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

-   [`Number.isFinite()`](number/isfinite)
-   [`Number.NaN`](number/nan)
-   [`Number.POSITIVE_INFINITY`](number/positive_infinity)
-   [`Number.NEGATIVE_INFINITY`](number/negative_infinity)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isFinite" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isFinite</a>
