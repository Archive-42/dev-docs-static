URLUtilsReadOnly.origin
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `URLUtilsReadOnly``.origin` read-only property is a [`DOMString`](../domstring) containing the Unicode serialization of the origin of the represented URL, that is, for http and https, the scheme followed by `'://'`, followed by the domain, followed by `':'`, followed by the port (the default port, `80` and `443` respectively, if explicitly specified). For URL using `file:` scheme, the value is browser dependant.

This version of `origin` is implemented by [`WorkerLocation`](../workerlocation) for use on workers.

Syntax
------

    string = object.origin;

Examples
--------

    // On this page, returns the origin
    var result = self.location.origin; // Returns:'https://developer.mozilla.org:443'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-url-origin">URL<br />
<span class="small">The definition of 'URLUtilsReadOnly.origin' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`origin`

No

No

29

No

No

No

No

No

29

No

No

No

See also
--------

-   The [`URLUtilsReadOnly`](../urlutilsreadonly) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLUtilsReadOnly/origin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLUtilsReadOnly/origin</a>
