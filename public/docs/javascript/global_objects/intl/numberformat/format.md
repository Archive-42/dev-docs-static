Intl.NumberFormat.prototype.format()
====================================

The `Intl.NumberFormat.prototype.format()` method formats a number according to the locale and formatting options of this [`Intl/NumberFormat`](../numberformat) object.

Syntax
------

    format(number)

### Parameters

`number`  
A [`Number`](../../number) or [`BigInt`](../../bigint) to format.

Description
-----------

The `format` getter function formats a number into a string according to the locale and formatting options of this [`Intl/NumberFormat`](../numberformat) object.

Examples
--------

### Using format

Use the `format` getter function for formatting a single currency value, here for Russia:

    var options = { style: 'currency', currency: 'RUB' };
    var numberFormat = new Intl.NumberFormat('ru-RU', options);
    console.log(numberFormat.format(654321.987));
    // → "654 321,99 руб."

### Using format with map

Use the `format` getter function for formatting all numbers in an array. Note that the function is bound to the [`Intl/NumberFormat`](../numberformat) from which it was obtained, so it can be passed directly to [`Array.prototype.map`](../../array/map). This is considered a historical artefact, as part of a convention which is no longer followed for new features, but is preserved to maintain compatibility with existing programs.

    var a = [123456.789, 987654.321, 456789.123];
    var numberFormat = new Intl.NumberFormat('es-ES');
    var formatted = a.map(n => numberFormat.format(n));
    console.log(formatted.join('; '));
    // → "123.456,789; 987.654,321; 456.789,123"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-intl.numberformat.prototype.format">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-intl.numberformat.prototype.format</span></a></td></tr></tbody></table>

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

`format`

24

12

Before Edge 18, numbers are rounded to 15 decimal digits. For example, `new Intl.NumberFormat('en-US').format(1000000000000005)` returns `"1,000,000,000,000,010"`.

29

11

In Internet Explorer 11, numbers are rounded to 15 decimal digits. For example, `new Intl.NumberFormat('en-US').format(1000000000000005)` returns `"1,000,000,000,000,010"`.

15

10

4.4

25

56

14

10

1.5

See also
--------

-   [`Intl.NumberFormat`](../numberformat)
-   [`Number.prototype.toLocaleString()`](../../number/tolocalestring)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/format" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/format</a>
