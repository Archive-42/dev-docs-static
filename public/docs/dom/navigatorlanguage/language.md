NavigatorLanguage.language
==========================

The `NavigatorLanguage.language` read-only property returns a string representing the preferred language of the user, usually the language of the browser UI.

Syntax
------

    const lang = navigator.language

### Value

A [`DOMString`](../domstring). *`lang`* stores a string representing the language version as defined in [BCP 47](https://tools.ietf.org/rfc/bcp/bcp47.txt). Examples of valid language codes include "en", "en-US", "fr", "fr-FR", "es-ES", etc.

Note that in Safari on iOS prior to 10.2, the country code returned is lowercase: "en-us", "fr-fr" etc.

Example
-------

    if (/^en\b/.test(navigator.language)) {
      doLangSelect(window.navigator.language);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-navigator-language">HTML Living Standard<br />
<span class="small">The definition of 'NavigatorLanguage: language' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`language`

1

12

1

Prior to Firefox 4, this property's value was also part of the user agent string, as reported by `navigator.userAgent`. Starting in Firefox 5, this property's value is based on the value of the `Accept-Language` [HTTP header](https://developer.mozilla.org/docs/Web/HTTP/Headers).

11

Closest available (non-standard) properties are `userLanguage` and `browserLanguage`.

4

1

1

18

4

10.1

1

1.0

See also
--------

-   [`navigator.languages`](languages)
-   [`navigator`](../navigator)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage/language" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage/language</a>
