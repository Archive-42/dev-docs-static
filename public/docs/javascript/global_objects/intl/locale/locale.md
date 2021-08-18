Intl.Locale() constructor
=========================

The `Intl.Locale` constructor is a standard built-in property of the Intl object that represents a Unicode locale identifier.

Syntax
------

    new Intl.Locale(tag)
    new Intl.Locale(tag, options)

### Parameters

`tag`  
The Unicode locale identifier string.

`options`  
An object that contains configuration for the Locale. Keys are Unicode locale tags, values are valid Unicode tag values.

Examples
--------

### Basic usage

At its very simplest, the [`Intl.Locale`](locale) constructor takes a locale identifier string as its argument:

    let us = new Intl.Locale('en-US');

### Using the Locale constructor with an options object

The constructor also takes an optional configuration object argument, which can contain any of several extension types. For example, set the `hourCycle` property of the configuration object to your desired hour cycle type, and then pass it into the constructor:

    let us12hour = new Intl.Locale("en-US", {hourCycle: "h12"});
    console.log(us12hour.hourCycle); // Prints "h12"

Polyfill
--------

[formatjs Intl.Locale polyfill](https://formatjs.io/docs/polyfills/intl-locale)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-intl-locale-constructor">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-intl-locale-constructor</span></a></td></tr></tbody></table>

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

`Locale`

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

-   [`Intl.Collator`](../collator)
-   [Unicode locale identifiers spec](https://www.unicode.org/reports/tr35/#Canonical_Unicode_Locale_Identifiers)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/Locale" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/Locale</a>
