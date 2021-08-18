Location: port
==============

The `port` property of the [`Location`](../location) interface is a [`USVString`](../usvstring) containing the port number of the URL. If the URL does not contain an explicit port number, it will be set to `''`.

Syntax
------

    string = object.port;
    object.port = string;

Examples
--------

    // Let's an <a id="myAnchor" href="https://developer.mozilla.org:443/en-US/docs/Location.port"> element be in the document
    var anchor = document.getElementByID("myAnchor");
    var result = anchor.port; // Returns:'443'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-location-port">HTML Living Standard<br />
<span class="small">The definition of 'Location.port' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`port`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location/port" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location/port</a>
