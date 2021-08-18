Location: toString()
====================

The `toString()` stringifier method of the [`Location`](../location) interface returns a [`USVString`](../usvstring) containing the whole URL. It is a read-only version of [`Location.href`](href).

Syntax
------

    string = object.toString();

Examples
--------

    // Let's imagine an <a id="myAnchor" href="/en-US/docs/Location/toString"> element is in the document
    var anchor = document.getElementById("myAnchor");
    var result = anchor.toString(); // Returns: 'https://developer.mozilla.org/en-US/docs/Location/toString'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-location-href">HTML Living Standard</a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

52

12

22

11

Intranet sites are set to Compatibility View, which will emulate IE7 and omit `window.location.toString`.

?

1

52

52

22

?

1

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location/toString</a>
