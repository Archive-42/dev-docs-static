NDEFReader.write()
==================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `write()` method of [`NDEFReader`](../ndefreader) interface writes a specified message to a compatible NFC tag.

Syntax
------

    var sessionPromise = NDEFReader.write(message, options);

### Parameters

`message`  
The message to be written, either [`DOMString`](../domstring) or [`BufferSource`](../buffersource) or <span class="page-not-created">`NDEFMessageInit`</span>.

 `options` <span class="badge inline optional">Optional</span>   
-   `overwrite` -- [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) specifying whether or not existing record should be overwritten, if such exists.
-   `signal` -- optional [`AbortSignal`](../abortsignal) that allows to cancel this write operation.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with `undefined` when and if the message transfer is successfully completed.

Exceptions
----------

This method doesn't throw true exceptions; instead, it rejects the returned promise, passing into it a [`DOMException`](../domexception) whose `name` is one of the following:

`AbortError`  
The write operation was aborted with [`AbortSignal`](../abortsignal) passed in options.

`NotAllowedError`  
The permission for this operation was rejected or `overwrite` is `false` and there are already records on the tag.

`NotSupportedError`  
There is no NFC adapter compatible with Web NFC, or the available NFC adapter does not support pushing messages, or connection can not be established.

`NotReadableError`  
The UA is not allowed to access underlying NFC adapter (e.g., due to user preference).

`NetworkError`  
Transfer failed after it already started (e.g., the tag was removed from the reader).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/web-nfc/#dom-ndefreader-write">Web NFC, write()</a></td><td>Draft</td><td>Initial definition.</td></tr></tbody></table>

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

`write`

No

No

No

No

No

No

No

89

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NDEFReader/write" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NDEFReader/write</a>
