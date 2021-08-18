Location: href
==============

The `href` property of the [`Location`](../location) interface is a stringifier that returns a [`USVString`](../usvstring) containing the whole URL, and allows the href to be updated.

Setting the value of `href` *navigates* to the provided URL. If you want *redirection*, use [`Location.replace()`](replace).

Syntax
------

    string = object.href;
    object.href = string;

Examples
--------

    // Lets imagine an <a id="myAnchor" href="https://developer.mozilla.org/en-US/Location/href"> element is in the document
    var anchor = document.getElementById("myAnchor");
    var result = anchor.href; // Returns: 'https://developer.mozilla.org/en-US/Location/href'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-location-href">HTML Living Standard<br />
<span class="small">The definition of 'href' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`href`

1

12

1

3

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location/href" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location/href</a>
