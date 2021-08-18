Intl.Locale.prototype.toString()
================================

The `Intl.Locale.prototype.toString()` returns the Locale's full [locale identifier string](https://www.unicode.org/reports/tr35/#Unicode_locale_identifier).

Syntax
------

    toString()

### Return value

The locale's Unicode locale identifier string.

Description
-----------

The `locale` object is a JavaScript representation of a concept Unicode locale identifier. Information about a particular locale (language, script, calendar type, etc.) can be encoded in a locale identifier string. To make it easier to work with these locale identifiers, the `locale` object was introduced to JavaScript. Calling the `toString` method on a Locale object will return the identifier string for that particular Locale. The `toString` method allows `locale` instances to be provided as an argument to existing `Intl` constructors, serialized in JSON, or any other context where an exact string representation is useful.

Examples
--------

### Using toString

    let myLocale = new Intl.Locale("fr-Latn-FR", {hourCycle: "h24", calendar: "gregory"});
    console.log(myLocale.baseName); // Prints "fr-Latn-FR"
    console.log(myLocale.toString()); // Prints "fr-Latn-FR-u-ca-gregory-hc-h24"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-Intl.Locale.prototype.toString">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-Intl.Locale.prototype.toString</span></a></td></tr></tbody></table>

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

74

79

75

No

62

14

74

74

79

53

14

11.0

See also
--------

-   [`Intl.Locale`](../locale)
-   [`Intl.Locale.baseName`](basename)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/toString</a>
