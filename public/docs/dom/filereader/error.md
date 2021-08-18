FileReader.error
================

The [`FileReader`](../filereader) `error` property returns the error that occurred while reading the file.

Syntax
------

    var error = instanceOfFileReader.error

Value
-----

A [`DOMError`](../domerror) containing the relevant error. In Chrome 48+/Firefox 58+ this property returns a [`DOMException`](../domexception) because `DOMError` has been removed from the DOM standard.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dom-filereader-error">File API<br />
<span class="small">The definition of 'FileReader: error' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`error`

7

12

3.6

\["Prior to Firefox 13, the `error` property returned a `FileError` object.", "From Firefox 13 to Firefox 58, the `error` property returned a `DOMError` object.", "From Firefox 58, the `error` property returns a `DOMException` object."\]

10

The `error` property returns a `DOMError` object.

11

6.1

The `error` property returns a `DOMError` object.

≤37

Yes

32

\["From Firefox 32 to Firefox 58, the `error` property returned a `DOMError` object.", "From Firefox 58, the `error` property returns a `DOMException` object."\]

11

6.1

The `error` property returns a `DOMError` object.

Yes

See also
--------

-   [`FileReader`](../filereader)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReader/error" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReader/error</a>
