Location: protocol
==================

The `protocol` property of the [`Location`](../location) interface is a [`USVString`](../usvstring) representing the protocol scheme of the URL, including the final `':'`.

Syntax
------

    string = object.protocol;
    object.protocol = string;

Examples
--------

    // Let's an <a id="myAnchor" href="https://developer.mozilla.org/en-US/Location.protocol"> element be in the document
    var anchor = document.getElementById("myAnchor");
    var result = anchor.protocol; // Returns:'https:'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-location-protocol">HTML Living Standard<br />
<span class="small">The definition of 'protocol' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`protocol`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location/protocol" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location/protocol</a>
