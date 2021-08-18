Number.prototype.toLocaleString()
=================================

The `toLocaleString()` method returns a string with a language-sensitive representation of this number.

Syntax
------

    toLocaleString()
    toLocaleString(locales)
    toLocaleString(locales, options)

### Parameters

The `locales` and `options` arguments customize the behavior of the function and let applications specify the language whose formatting conventions should be used. In implementations, which ignore the `locales` and `options` arguments, the locale used and the form of the string returned are entirely implementation dependent.

See the [`Intl.NumberFormat()` constructor](../intl/numberformat/numberformat) for details on these parameters and how to use them.

### Return value

A string with a language-sensitive representation of the given number.

Performance
-----------

When formatting large numbers of numbers, it is better to create a [`Intl/NumberFormat`](../intl/numberformat) object and use the function provided by its [`Intl/NumberFormat/format`](../intl/numberformat/format) property.

Examples
--------

### Using `toLocaleString`

In basic use without specifying a locale, a formatted string in the default locale and with default options is returned.

    var number = 3500;

    console.log(number.toLocaleString()); // Displays "3,500" if in U.S. English locale

### Checking for support for `locales` and `options` arguments

The `locales` and `options` arguments are not supported in all browsers yet. To check for support in ES5.1 and later implementations, the requirement that illegal language tags are rejected with a [`RangeError`](../rangeerror) exception can be used:

    function toLocaleStringSupportsLocales() {
      var number = 0;
      try {
        number.toLocaleString('i');
      } catch (e) {
        return e.name === 'RangeError';
      }
      return false;
    }

Prior to ES5.1, implementations were not required to throw a range error exception if `toLocaleString` is called with arguments.

A check that works in all hosts, including those supporting ECMA-262 prior to ed 5.1, is to test for the features specified in ECMA-402 that are required to support regional options for `Number.prototype.toLocaleString` directly:

    function toLocaleStringSupportsOptions() {
      return !!(typeof Intl == 'object' && Intl && typeof Intl.NumberFormat == 'function');
    }

This tests for a global `Intl` object, checks that it's not `null` and that it has a `NumberFormat` property that is a function.

### Using `locales`

This example shows some of the variations in localized number formats. In order to get the format of the language used in the user interface of your application, make sure to specify that language (and possibly some fallback languages) using the `locales` argument:

    var number = 123456.789;

    // German uses comma as decimal separator and period for thousands
    console.log(number.toLocaleString('de-DE'));
    // → 123.456,789

    // Arabic in most Arabic speaking countries uses Eastern Arabic digits
    console.log(number.toLocaleString('ar-EG'));
    // → ١٢٣٤٥٦٫٧٨٩

    // India uses thousands/lakh/crore separators
    console.log(number.toLocaleString('en-IN'));
    // → 1,23,456.789

    // the nu extension key requests a numbering system, e.g. Chinese decimal
    console.log(number.toLocaleString('zh-Hans-CN-u-nu-hanidec'));
    // → 一二三,四五六.七八九

    // when requesting a language that may not be supported, such as
    // Balinese, include a fallback language, in this case Indonesian
    console.log(number.toLocaleString(['ban', 'id']));
    // → 123.456,789

### Using `options`

The results provided by `toLocaleString` can be customized using the `options` argument:

    var number = 123456.789;

    // request a currency format
    console.log(number.toLocaleString('de-DE', { style: 'currency', currency: 'EUR' }));
    // → 123.456,79 €

    // the Japanese yen doesn't use a minor unit
    console.log(number.toLocaleString('ja-JP', { style: 'currency', currency: 'JPY' }))
    // → ￥123,457

    // limit to three significant digits
    console.log(number.toLocaleString('en-IN', { maximumSignificantDigits: 3 }));
    // → 1,23,000

    // Use the host default language with options for number formatting
    var num = 30000.65;
    console.log(num.toLocaleString(undefined, {minimumFractionDigits: 2, maximumFractionDigits: 2}));
    // → "30,000.65" where English is the default language, or
    // → "30.000,65" where German is the default language, or
    // → "30 000,65" where French is the default language

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-number.prototype.tolocalestring">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-number.prototype.tolocalestring</span></a></td></tr><tr class="even"><td><a href="https://tc39.es/ecma402/#sup-number.prototype.tolocalestring">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sup-number.prototype.tolocalestring</span></a></td></tr></tbody></table>

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

1

12

Before Edge 18, numbers are rounded to 15 decimal digits. For example, `(1000000000000005).toLocaleString('en-US')` returns `"1,000,000,000,000,010"`.

1

5

In Internet Explorer 11, numbers are rounded to 15 decimal digits. For example, `(1000000000000005).toLocaleString('en-US')` returns `"1,000,000,000,000,010"`.

4

1

1

18

4

10.1

1

1.0

`locales`

24

12

29

11

15

10

4.4

26

56

14

10

1.5

`options`

24

12

29

11

15

10

4.4

26

56

14

10

1.5

See also
--------

-   [`Number.prototype.toString()`](tostring)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toLocaleString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toLocaleString</a>
