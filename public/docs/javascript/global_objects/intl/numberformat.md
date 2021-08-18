Intl.NumberFormat
=================

The `Intl.NumberFormat` object enables language-sensitive number formatting.

Constructor
-----------

[`Intl.NumberFormat()`](numberformat/numberformat)  
Creates a new `NumberFormat` object.

Static methods
--------------

[`Intl.NumberFormat.supportedLocalesOf()`](numberformat/supportedlocalesof)  
Returns an array containing those of the provided locales that are supported without having to fall back to the runtime's default locale.

Instance methods
----------------

[`Intl.NumberFormat.prototype.format()`](numberformat/format)  
Getter function that formats a number according to the locale and formatting options of this [`Intl/NumberFormat`](numberformat) object.

[`Intl.NumberFormat.prototype.formatToParts()`](numberformat/formattoparts)  
Returns an [`Array`](../array) of objects representing the number string in parts that can be used for custom locale-aware formatting.

[`Intl.NumberFormat.prototype.resolvedOptions()`](numberformat/resolvedoptions)  
Returns a new object with properties reflecting the locale and collation options computed during initialization of the object.

Examples
--------

### Basic usage

In basic use without specifying a locale, a formatted string in the default locale and with default options is returned.

    var number = 3500;

    console.log(new Intl.NumberFormat().format(number));
    // → '3,500' if in US English locale

### Using locales

This example shows some of the variations in localized number formats. In order to get the format of the language used in the user interface of your application, make sure to specify that language (and possibly some fallback languages) using the `locales` argument:

    var number = 123456.789;

    // German uses comma as decimal separator and period for thousands
    console.log(new Intl.NumberFormat('de-DE').format(number));
    // → 123.456,789

    // Arabic in most Arabic speaking countries uses real Arabic digits
    console.log(new Intl.NumberFormat('ar-EG').format(number));
    // → ١٢٣٤٥٦٫٧٨٩

    // India uses thousands/lakh/crore separators
    console.log(new Intl.NumberFormat('en-IN').format(number));
    // → 1,23,456.789

    // the nu extension key requests a numbering system, e.g. Chinese decimal
    console.log(new Intl.NumberFormat('zh-Hans-CN-u-nu-hanidec').format(number));
    // → 一二三,四五六.七八九

    // when requesting a language that may not be supported, such as
    // Balinese, include a fallback language, in this case Indonesian
    console.log(new Intl.NumberFormat(['ban', 'id']).format(number));
    // → 123.456,789

### Using options

The results can be customized using the `options` argument:

    var number = 123456.789;

    // request a currency format
    console.log(new Intl.NumberFormat('de-DE', { style: 'currency', currency: 'EUR' }).format(number));
    // → 123.456,79 €

    // the Japanese yen doesn't use a minor unit
    console.log(new Intl.NumberFormat('ja-JP', { style: 'currency', currency: 'JPY' }).format(number));
    // → ￥123,457

    // limit to three significant digits
    console.log(new Intl.NumberFormat('en-IN', { maximumSignificantDigits: 3 }).format(number));
    // → 1,23,000

### Using style and unit

    console.log(new Intl.NumberFormat('pt-PT',  {
        style: 'unit',
        unit: 'kilometer-per-hour'
    }).format(50));
    // → 50 km/h

    console.log((16).toLocaleString('en-GB', {
        style: 'unit',
        unit: 'liter',
        unitDisplay: 'long'
    }));
    // → 16 litres

Polyfill
--------

[formatjs Intl.NumberFormat polyfill](https://formatjs.io/docs/polyfills/intl-numberformat)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#numberformat-objects">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#numberformat-objects</span></a></td></tr></tbody></table>

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

`NumberFormat`

24

12

29

11

15

10

4.4

25

56

14

10

1.5

`NumberFormat`

24

12

29

11

15

10

4.4

25

56

14

10

1.5

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

`formatToParts`

64

12

58

No

51

13

64

64

58

47

13

9.0

`resolvedOptions`

24

12

29

11

15

10

4.4

25

56

14

10

1.5

`supportedLocalesOf`

24

12

29

11

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

-   [`Intl`](../intl)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat</a>
