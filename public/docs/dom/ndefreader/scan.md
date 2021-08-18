# NDEFReader.scan()

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `scan()` method of [`NDEFReader`](../ndefreader) interface reads NDEF records from compatible NFC devices, e.g., NDEF NFC tags.

## Syntax

    var readerPromise = NDEFReader.scan(options);

### Parameters

`options` <span class="badge inline optional">Optional</span>

- `signal` -- optional [`AbortSignal`](../abortsignal) that allows to cancel this `scan()` operation.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with `undefined` immediately after scheduling read operations for the NFC adapter.

## Exceptions

This method doesn't throw true exceptions; instead, it rejects the returned promise, passing into it a [`DOMException`](../domexception) whose `name` is one of the following:

`AbortError`  
The scan operation was aborted with [`AbortSignal`](../abortsignal) passed in options.

`InvalidStateError`  
There's already an ongoing scan.

`NotAllowedError`  
The permission for this operation was rejected.

`NotSupportedError`  
There is no NFC adapter compatible with Web NFC, or a connection can not be established.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/web-nfc/#dom-ndefreader-scan">Web NFC, scan()</a></td><td>Draft</td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`scan`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NDEFReader/scan" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NDEFReader/scan</a>
