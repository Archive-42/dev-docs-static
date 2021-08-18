Location: search
================

The `search` property of the [`Location`](../location) interface is a search string, also called a *query string*; that is, a [`USVString`](../usvstring) containing a `'?'` followed by the parameters of the URL.

Modern browsers provide `URLSearchParams` and `URL.searchParams` to make it easy to parse out the parameters from the querystring.

Syntax
------

    string = object.search;
    object.search = string;

Examples
--------

    // Let an <a id="myAnchor" href="/en-US/docs/Location.search?q=123"> element be in the document
    var anchor = document.getElementById("myAnchor");
    var queryString = anchor.search; // Returns:'?q=123'

    // Further parsing:
    let params = new URLSearchParams(queryString);
    let q = parseInt(params.get("q")); // is the number 123

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-location-search">HTML Living Standard<br />
<span class="small">The definition of 'search' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`search`

1

12

1

Before Firefox 53, the `search` property returned wrong parts of the URL. For example, for a URL of http://z.com/x?a=true&b=false, `search` would return "", rather than "?a=true&b=false".

3

≤12.1

1

1

18

4

Before Firefox 53, the `search` property returned wrong parts of the URL. For example, for a URL of http://z.com/x?a=true&b=false, `search` would return "", rather than "?a=true&b=false".

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location/search" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location/search</a>
