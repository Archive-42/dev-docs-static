FileReader.readAsText()
=======================

The `readAsText()` method is used to read the contents of the specified [`Blob`](../blob) or [`File`](../file). When the read operation is complete, the [`readyState`](readystate) is changed to `DONE`, the `loadend` event is triggered, and the [`result`](result) property contains the contents of the file as a text string.

**Newer API available**  
The [`Blob.text()`](../blob/text) method is a newer promise-based API to read a file as text.

Syntax
------

    instanceOfFileReader.readAsText(blob[, encoding]);

### Parameters

`blob`  
The [`Blob`](../blob) or [`File`](../file) from which to read.

 `encoding` <span class="badge inline optional">Optional</span>   
A string specifying the encoding to use for the returned data. By default, UTF-8 is assumed if this parameter is not specified.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#readAsDataText">File API<br />
<span class="small">The definition of 'readAsText()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`readAsText`

7

12

3.6

10

11

6

≤37

18

32

11

6

1.0

See also
--------

-   [`FileReader`](../filereader)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsText</a>
