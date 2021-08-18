Location: host
==============

The `host` property of the [`Location`](../location) interface is a [`USVString`](../usvstring) containing the host, that is the *hostname*, and then, if the *port* of the URL is nonempty, a `':'`, and the *port* of the URL.

Syntax
------

    string = object.host;
    object.host = string;

Examples
--------

    var anchor = document.createElement("a");

    anchor.href = "https://developer.mozilla.org/en-US/Location.host"
    anchor.host == "developer.mozilla.org"

    anchor.href = "https://developer.mozilla.org:443/en-US/Location.host"
    anchor.host == "developer.mozilla.org"
    // The port number is not included because 443 is the scheme's default port

    anchor.href = "https://developer.mozilla.org:4097/en-US/Location.host"
    anchor.host == "developer.mozilla.org:4097"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-location-host">HTML Living Standard<br />
<span class="small">The definition of 'host' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`host`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location/host" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location/host</a>
