TypedArray.prototype.toLocaleString()
=====================================

The `toLocaleString()` method returns a string representing the elements of the typed array. The elements are converted to strings and are separated by a locale-specific string (such as a comma “,”). This method has the same algorithm as [`Array.prototype.toLocaleString()`](../array/tolocalestring) and, as the typed array elements are numbers, the same algorithm as [`Number.prototype.toLocaleString()`](../number/tolocalestring) applies for each element. *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

Syntax
------

    toLocaleString()
    toLocaleString(locales)
    toLocaleString(locales, options)

### Parameters

The `locales` and `options` arguments customize the behavior of the function and let applications specify the language whose formatting conventions should be used. In implementations, which ignore the `locales` and `options` arguments, the locale used and the form of the string returned are entirely implementation dependent.

See the [`Intl.NumberFormat()`](../intl/numberformat/numberformat) constructor for details on these parameters and how to use them.

### Return value

A string representing the elements of the typed array.

Examples
--------

### Using toLocaleString

    var uint = new Uint32Array([2000, 500, 8123, 12, 4212]);

    uint.toLocaleString();
    // if run in a de-DE locale
    // "2.000,500,8.123,12,4.212"

    uint.toLocaleString('en-US');
    // "2,000,500,8,123,12,4,212"

    uint.toLocaleString('ja-JP', { style: 'currency', currency: 'JPY' });
    // "￥2,000,￥500,￥8,123,￥12,￥4,212"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.tolocalestring</span></a></td></tr></tbody></table>

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

`toLocaleString`

7

12

51

10

11.6

5.1

≤37

18

51

12

5

1.0

See also
--------

-   [`Array.prototype.toLocaleString()`](../array/tolocalestring)
-   [`Number.prototype.toLocaleString()`](../number/tolocalestring)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/toLocaleString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/toLocaleString</a>
