FileReader.abort()
==================

The `abort` method aborts the read operation. Upon return, the [`readyState`](readystate) will be `DONE`.

Syntax
------

    instanceOfFileReader.abort();

### Exceptions

`DOM_FILE_ABORT_ERR`  
Thrown when `abort` is called while no read operation is in progress (that is, the state isn't `LOADING`).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#abort">File API<br />
<span class="small">The definition of 'abort()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`abort`

7

12

3.6

10

11

6

≤37

Yes

32

11

6

Yes

See also
--------

-   [`FileReader`](../filereader)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReader/abort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReader/abort</a>
