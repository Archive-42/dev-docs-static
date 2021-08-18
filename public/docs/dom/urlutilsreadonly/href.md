URLUtilsReadOnly.href
=====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `URLUtilsReadOnly``.href` read-only property is a stringifier that returns a [`DOMString`](../domstring) containing the whole URL.

Syntax
------

    string = object.href;

Examples
--------

    // In a Web worker, on the page https://developer.mozilla.org/en-US/URLUtilsReadOnly.href
    var result = window.self.href; // Returns:'https://developer.mozilla.org/en-US/URLUtilsReadOnly.href'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-url-href">URL<br />
<span class="small">The definition of 'URLUtilsReadOnly.href' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLUtilsReadOnly/href" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLUtilsReadOnly/href</a>
