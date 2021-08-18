BigInt.prototype.toLocaleString()
=================================

The `toLocaleString()` method returns a string with a language-sensitive representation of this BigInt.

Syntax
------

    toLocaleString()
    toLocaleString(locales)
    toLocaleString(locales, options)

### Parameters

The `locales` and `options` arguments customize the behavior of the function and let applications specify the language whose formatting conventions should be used. In implementations that ignore the `locales` and `options` arguments, the locale used and the form of the string returned are entirely implementation-dependent.

See the [`Intl.NumberFormat()` constructor](../intl/numberformat/numberformat) for details on these parameters and how to use them.

### Return value

A string with a language-sensitive representation of the given BigInt.

Performance
-----------

When formatting large numbers of numbers, it is better to create a [`NumberFormat`](../intl/numberformat) object and use the function provided by its [`NumberFormat.format`](../intl/numberformat/format) property.

Examples
--------

### Using `toLocaleString`

In basic use without specifying a locale, a formatted string in the default locale and with default options is returned.

    var bigint = 3500n;

    bigint.toLocaleString();
    // Displays "3,500" if in U.S. English locale

### Using `locales`

This example shows some of the variations in localized number formats. In order to get the format of the language used in the user interface of your application, make sure to specify that language (and possibly some fallback languages) using the `locales` argument:

    var bigint = 123456789123456789n;

    // German uses period for thousands
    console.log(bigint.toLocaleString('de-DE'));
    // → 123.456.789.123.456.789

    // Arabic in most Arabic speaking countries uses Eastern Arabic digits
    console.log(bigint.toLocaleString('ar-EG'));
    // → ١٢٣٬٤٥٦٬٧٨٩٬١٢٣٬٤٥٦٬٧٨٩

    // India uses thousands/lakh/crore separators
    console.log(bigint.toLocaleString('en-IN'));
    // → 1,23,45,67,89,12,34,56,789

    // the nu extension key requests a numbering system, e.g. Chinese decimal
    console.log(bigint.toLocaleString('zh-Hans-CN-u-nu-hanidec'));
    // → 一二三,四五六,七八九,一二三,四五六,七八九

    // when requesting a language that may not be supported, such as
    // Balinese, include a fallback language, in this case Indonesian
    console.log(bigint.toLocaleString(['ban', 'id']));
    // → 123.456.789.123.456.789

### Using `options`

The results provided by `toLocaleString` can be customized using the `options` argument:

    var bigint = 123456789123456789n;

    // request a currency format
    console.log(bigint.toLocaleString('de-DE', { style: 'currency', currency: 'EUR' }));
    // → 123.456.789.123.456.789,00 €

    // the Japanese yen doesn't use a minor unit
    console.log(bigint.toLocaleString('ja-JP', { style: 'currency', currency: 'JPY' }))
    // → ￥123,456,789,123,456,789

    // limit to three significant digits
    console.log(bigint.toLocaleString('en-IN', { maximumSignificantDigits: 3 }));
    // → 1,23,00,00,00,00,00,00,000

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sup-bigint.prototype.tolocalestring">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sup-bigint.prototype.tolocalestring</span></a></td></tr></tbody></table>

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

`locales`

76

79

70

No

No

14

76

76

79

54

14

No

`options`

76

79

70

No

No

14

76

76

79

54

14

No

See also
--------

-   [`BigInt.toString()`](tostring)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt/toLocaleString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt/toLocaleString</a>
