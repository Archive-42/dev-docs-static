URLUtilsReadOnly.pathname
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `URLUtilsReadOnly``.pathname` read-only property returns a [`USVString`](../usvstring) containing an initial `'/'` followed by the path of the URL, not including the query string or fragment.

Syntax
------

    string = object.pathname;

Examples
--------

    // In a Web worker, on the page https://developer.mozilla.org/en-US/URLUtilsReadOnly.pathname
    var result = window.self.pathname; // Returns:'/en-US/URLUtilsReadOnly.pathname'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-url-pathname">URL<br />
<span class="small">The definition of 'URLUtilsReadOnly.pathname' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

No

No

3.5

No

No

No

No

No

4

No

No

No

See also
--------

-   The [`URLUtilsReadOnly`](../urlutilsreadonly) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLUtilsReadOnly/pathname" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLUtilsReadOnly/pathname</a>
