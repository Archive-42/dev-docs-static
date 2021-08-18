USBOutTransferResult
====================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `USBOutTransferResult` interface of the [WebUSB API](webusb_api) provides the result from a call to the `transferOut()` and `controlTransferOut()` methods of the `USBDevice` interface. It represents the result from requesting a transfer of data from the USB host to the USB device.

Constructor
-----------

<span class="page-not-created">`USBOutTransferResult.USBOutTransferResult()`</span>  
Creates a new `USBOutTransferResult` object with the provided `status` and `bytesWritten` fields.

Properties
----------

 <span class="page-not-created">`USBOutTransferResult.bytesWritten`</span><span class="badge inline readonly">Read only </span>   
Returns the number of bytes from the transfer request that were sent to the device.

 <span class="page-not-created">`USBOutTransferResult.status`</span><span class="badge inline readonly">Read only </span>   
Returns the status of the transfer request, one of:

-   `"ok"` - The transfer was successful.
-   `"stall"` - The device indicated an error by generating a stall condition on the endpoint. A stall on a bulk or interrupt endpoint must be cleared by calling `clearHalt()` before `transferOut()` can be called again.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#usbouttransferresult">WebUSB<br />
<span class="small">The definition of 'USBOutTransferResult' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`USBOutTransferResult`

61

79

No

No

48

No

No

61

No

45

No

8.0

`USBOutTransferResult`

61

79

No

No

48

No

No

61

No

45

No

8.0

`bytesWritten`

61

79

No

No

48

No

No

61

No

45

No

8.0

`status`

61

79

No

No

48

No

No

61

No

45

No

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBOutTransferResult" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBOutTransferResult</a>
