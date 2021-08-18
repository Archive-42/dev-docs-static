Intl.DisplayNames.prototype.of()
================================

The `Intl.DisplayNames.prototype.of()` method receives a code and returns a string based on the locale and options provided when instantiating Intl.DisplayNames.

Syntax
------

    of(code)

### Parameters

`code`  
The `code` to provide depends on the `type`:

-   If the type is "region", code should be either an [ISO-3166 two letters region code](https://www.iso.org/iso-3166-country-codes.html), or a [three digits UN M49 Geographic Regions](https://unstats.un.org/unsd/methodology/m49/).
-   If the type is "script", code should be an [ISO-15924 four letters script code](https://unicode.org/iso15924/iso15924-codes.html).
-   If the type is "language", code should be a *languageCode* \["-" *scriptCode*\] \["-" *regionCode* \] \*("-" *variant* ) subsequence of the unicode\_language\_id grammar in [UTS 35's Unicode Language and Locale Identifiers grammar](https://unicode.org/reports/tr35/#Unicode_language_identifier). *languageCode* is either a two letters ISO 639-1 language code or a three letters ISO 639-2 language code.
-   If the type is "currency", code should be a [3-letter ISO 4217 currency code](https://www.iso.org/iso-4217-currency-codes.html).

### Return value

A language-specific formatted string.

Examples
--------

### Using the of method

    let regionNames = new Intl.DisplayNames(['en'], {type: 'region'});
    regionNames.of('419'); // "Latin America"

    let languageNames = new Intl.DisplayNames(['en'], {type: 'language'});
    languageNames.of('fr'); // "French"

    let currencyNames = new Intl.DisplayNames(['en'], {type: 'currency'});
    currencyNames.of('EUR'); // "Euro"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-Intl.DisplayNames.prototype.of">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-Intl.DisplayNames.prototype.of</span></a></td></tr></tbody></table>

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

`of`

81

81

86

No

68

14.1

81

81

86

58

14.5

No

See also
--------

-   [`Intl.DisplayNames`](../displaynames)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DisplayNames/of" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DisplayNames/of</a>
