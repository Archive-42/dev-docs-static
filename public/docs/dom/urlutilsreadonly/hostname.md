URLUtilsReadOnly.hostname
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `URLUtilsReadOnly``.hostname` read-only property returns a [`DOMString`](../domstring) containing the domain of the URL.

Syntax
------

    string = object.hostname;

Examples
--------

    // In a Web worker, on the page https://developer.mozilla.org/en-US/URLUtilsReadOnly.hostname
    var result = window.self.hostname; // Returns:'developer.mozilla.org'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-url-hostname">URL<br />
<span class="small">The definition of 'URLUtilsReadOnly.hostname' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`hostname`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLUtilsReadOnly/hostname" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLUtilsReadOnly/hostname</a>
