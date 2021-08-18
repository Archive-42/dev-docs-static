Intl.DateTimeFormat.supportedLocalesOf()
========================================

The `Intl.DateTimeFormat.supportedLocalesOf()` method returns an array containing those of the provided locales that are supported in date and time formatting without having to fall back to the runtime's default locale.

Syntax
------

    Intl.DateTimeFormat.supportedLocalesOf(locales)
    Intl.DateTimeFormat.supportedLocalesOf(locales, options)

### Parameters

`locales`  
A string with a BCP 47 language tag, or an array of such strings. For the general form of the `locales` argument, see the [Intl](../../intl#locale_identification_and_negotiation) page.

 `options` <span class="badge inline optional">Optional</span>   
An object that may have the following property:

`localeMatcher`  
The locale matching algorithm to use. Possible values are "`lookup`" and "`best fit`"; the default is "`best fit`". For information about this option, see the [Intl](../../intl#locale_negotiation) page.

### Return value

An array of strings representing a subset of the given locale tags that are supported in date and time formatting without having to fall back to the runtime's default locale.

Description
-----------

Returns an array with a subset of the language tags provided in `locales`. The language tags returned are those for which the runtime supports a locale in date and time formatting that the locale matching algorithm used considers a match, so that it wouldn't have to fall back to the default locale.

Examples
--------

### Using supportedLocalesOf()

Assuming a runtime that supports Indonesian and German but not Balinese in date and time formatting, `supportedLocalesOf` returns the Indonesian and German language tags unchanged, even though `pinyin` collation is neither relevant to date and time formatting nor used with Indonesian, and a specialized German for Indonesia is unlikely to be supported. Note the specification of the "`lookup`" algorithm here — a "`best fit`" matcher might decide that Indonesian is an adequate match for Balinese since most Balinese speakers also understand Indonesian, and therefore return the Balinese language tag as well.

    const locales = ['ban', 'id-u-co-pinyin', 'de-ID'];
    const options = { localeMatcher: 'lookup' };
    console.log(Intl.DateTimeFormat.supportedLocalesOf(locales, options).join(', '));
    // → "id-u-co-pinyin, de-ID"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-intl.datetimeformat.supportedlocalesof">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-intl.datetimeformat.supportedlocalesof</span></a></td></tr></tbody></table>

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

-   [`Intl.DateTimeFormat`](../datetimeformat)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/supportedLocalesOf" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/supportedLocalesOf</a>
