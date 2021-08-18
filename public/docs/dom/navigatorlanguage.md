NavigatorLanguage
=================

`NavigatorLanguage` contains methods and properties related to the language of the navigator.

There is no object of type `NavigatorLanguage`, but other interfaces, like [`Navigator`](navigator) or [`WorkerNavigator`](workernavigator), implement it.

Properties
----------

*The `NavigatorLanguage` interface doesn't inherit any property.*

 [`NavigatorLanguage.language`](navigatorlanguage/language) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) representing the preferred language of the user, usually the language of the browser UI. The `null` value is returned when this is unknown.

 [`NavigatorLanguage.languages`](navigatorlanguage/languages) <span class="badge inline readonly">Read only </span>   
Returns an array of [`DOMString`](domstring) representing the languages known to the user, by order of preference.

Methods
-------

*The `NavigatorLanguage` interface neither implements, nor inherit any method.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#navigatorlanguage">HTML Living Standard<br />
<span class="small">The definition of 'NavigatorLanguage' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Since the <a href="https://www.w3.org/TR/html52/">HTML5</a> snapshot, the <code>languages</code> property has been added.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/#navigatorlanguage">HTML5<br />
<span class="small">The definition of 'NavigatorLanguage' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial specification; snapshot of an early version <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>.</td></tr></tbody></table>

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

`NavigatorLanguage`

1

12

1

11

4

1

1

18

4

10.1

1

1.0

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

See also
--------

-   The [`Navigator`](navigator) interface that implements it.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigatorLanguage</a>
