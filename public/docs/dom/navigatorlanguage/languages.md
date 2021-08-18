# NavigatorLanguage.languages

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `NavigatorLanguage.languages` read-only property returns an array of [`DOMString`](../domstring)s representing the user's preferred languages. The language is described using [BCP 47](https://datatracker.ietf.org/doc/html/bcp47) language tags. In the returned array they are ordered by preference with the most preferred language first.

The value of [`navigator.language`](language) is the first element of the returned array.

When its value changes, as the user's preferred languages are changed a `languagechange` event is fired on the [`Window`](../window) object.

The `Accept-Language` HTTP header in every HTTP request from the user's browser uses the same value for the `navigator.languages` property except for the extra `qvalues` (quality values) field (e.g. `en-US;q=0.8`).

## Syntax

    preferredLanguages = globalObj.navigator.languages

## Examples

    navigator.language   //"en-US"
    navigator.languages  //["en-US", "zh-CN", "ja-JP"]

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-navigator-languages">HTML Living Standard<br />
<span class="small">The definition of 'NavigatorLanguage: languages' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

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

`languages`

37

Before Chrome 65, `navigator.languages[0]` is not guaranteed to equal `navigator.language`.

16

32

In Firefox, the `navigator.languages` property's value is taken from the `intl.accept_languages` preference.

No

Closest available (non-standard) properties are `userLanguage` and `browserLanguage`.

24

10.1

37

Before version 65, `navigator.languages[0]` is not guaranteed to equal `navigator.language`.

37

Before Chrome 65, `navigator.languages[0]` is not guaranteed to equal `navigator.language`.

32

In Firefox, the `navigator.languages` property's value is taken from the `intl.accept_languages` preference.

24

10.3

3.0

## See also

- [`navigator.language`](language)
- [`Navigator`](../navigator)
- [`Window.onlanguagechange`](../windoweventhandlers/onlanguagechange)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage/languages" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage/languages</a>
