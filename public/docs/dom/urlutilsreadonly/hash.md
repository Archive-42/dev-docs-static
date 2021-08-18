URLUtilsReadOnly.hash
=====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `URLUtilsReadOnly``.hash` read-only property returns a [`DOMString`](../domstring) containing a `'#'` followed by the fragment identifier of the URL. The hash is not percent encoded.

Syntax
------

    string = object.hash;

Examples
--------

    // In a Web worker, on the page https://developer.mozilla.org/en-US/docs/URLUtilsReadOnly.hash#example
    var result = window.self.hash; // Returns:'#hash'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-url-hash">URL<br />
<span class="small">The definition of 'URLUtilsReadOnly.hash' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`hash`

No

No

38

3.5-38

Before Firefox 38, Firefox returned the hash percent encoded. This has been fixed to match the spec.

No

No

No

No

No

38

4-38

Before Firefox 38, Firefox returned the hash percent encoded. This has been fixed to match the spec.

No

No

No

See also
--------

-   The [`URLUtilsReadOnly`](../urlutilsreadonly) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLUtilsReadOnly/hash" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLUtilsReadOnly/hash</a>
