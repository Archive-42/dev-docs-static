Location: pathname
==================

The `pathname` property of the [`Location`](../location) interface is a [`USVString`](../usvstring) containing an initial `'/'` followed by the path of the URL (or the empty string if there is no path).

Syntax
------

    string = object.pathname;
    object.pathname = string;

Examples
--------

    // Let's an <a id="myAnchor" href="/en-US/docs/Location.pathname"> element be in the document
    var anchor = document.getElementById("myAnchor");
    var result = anchor.pathname; // Returns:'/en-US/docs/Location.pathname'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-location-pathname">HTML Living Standard<br />
<span class="small">The definition of 'pathname' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`pathname`

1

12

1

Before Firefox 53, the `pathname` property returned wrong parts of the URL. For example, for a URL of http://z.com/x?a=true&b=false, `pathname` would return "/x?a=true&b=false" rather than "/x".

3

Internet Explorer does not provide the leading slash character in the `pathname` (`docs/Web/API/Location` instead of `/docs/Web/API/Location`).

≤12.1

1

1

18

4

Before Firefox 53, the `pathname` property returned wrong parts of the URL. For example, for a URL of http://z.com/x?a=true&b=false, `pathname` would return "/x?a=true&b=false" rather than "/x".

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location/pathname" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location/pathname</a>
