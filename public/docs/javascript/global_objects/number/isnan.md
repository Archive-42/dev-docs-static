Number.isNaN()
==============

The `Number.isNaN()` method determines whether the passed value is [`NaN`](../nan) and its type is [`Number`](../number). It is a more robust version of the original, global [`isNaN()`](../isnan).

Syntax
------

    Number.isNaN(value)

### Parameters

`value`  
The value to be tested for [`NaN`](../nan).

### Return value

**true** if the given value is [`NaN`](../nan) and its type is [`Number`](../number); otherwise, **false**.

Description
-----------

Due to both equality operators, [`==`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#equality) and [`===`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#identity), evaluating to `false` when checking if [`NaN`](../nan) *is* [`NaN`](../nan), the function `Number.isNaN()` has become necessary. This situation is unlike all other possible value comparisons in JavaScript.

In comparison to the global [`isNaN()`](../isnan) function, `Number.isNaN()` doesn't suffer the problem of forcefully converting the parameter to a number. This means it is now safe to pass values that would normally convert to [`NaN`](../nan), but aren't actually the same value as [`NaN`](../nan). This also means that only values of the type number, that are also [`NaN`](../nan), return `true`.

Examples
--------

### Using isNaN

    Number.isNaN(NaN);        // true
    Number.isNaN(Number.NaN); // true
    Number.isNaN(0 / 0);      // true

    // e.g. these would have been true with global isNaN()
    Number.isNaN('NaN');      // false
    Number.isNaN(undefined);  // false
    Number.isNaN({});         // false
    Number.isNaN('blabla');   // false

    // These all return false
    Number.isNaN(true);
    Number.isNaN(null);
    Number.isNaN(37);
    Number.isNaN('37');
    Number.isNaN('37.37');
    Number.isNaN('');
    Number.isNaN(' ');

Polyfill
--------

The following works because NaN is the only value in JavaScript which is not equal to itself.

    Number.isNaN = Number.isNaN || function isNaN(input) {
        return typeof input === 'number' && input !== input;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-number.isnan">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-number.isnan</span></a></td></tr></tbody></table>

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

`isNaN`

25

12

15

No

15

9

≤37

25

15

14

9

1.5

See also
--------

-   [`Number`](../number)
-   [`isNaN()`](../isnan)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isNaN" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isNaN</a>
