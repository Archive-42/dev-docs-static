URLUtilsReadOnly.toString()
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `URLUtilsReadOnly``.toString()` stringifier method returns a [`DOMString`](../domstring) containing the whole URL. It is a synonym for [`URLUtilsReadOnly.href`](href).

Syntax
------

    string = object.toString();

Examples
--------

    // In a Web worker, on the page https://developer.mozilla.org/en-US/URLUtilsReadOnly.href
    var result = window.self.toString(); // Returns:'https://developer.mozilla.org/en-US/URLUtilsReadOnly.href'

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

`toString`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLUtilsReadOnly/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLUtilsReadOnly/toString</a>
