USBInTransferResult
===================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `USBInTransferResult` interface of the [WebUSB API](webusb_api) provides the result from a call to the `transferIn()` and `controlTransferIn()` methods of the `USBDevice` interface. It represents the result from requesting a transfer of data from the USB device to the USB host.

Constructor
-----------

<span class="page-not-created">`USBInTransferResult.USBInTransferResult()`</span>  
Creates a new `USBInTransferResult` object with the provided `status` and `data` fields.

Properties
----------

 <span class="page-not-created">`USBInTransferResult.data`</span><span class="badge inline readonly">Read only </span>   
Returns a `DataView` object containing the data received from the USB device, if any.

 <span class="page-not-created">`USBInTransferResult.status`</span><span class="badge inline readonly">Read only </span>   
Returns the status of the transfer request, one of:

-   `"ok"` - The transfer was successful.
-   `"stall"` - The device indicated an error by generating a stall condition on the endpoint. A stall on the control endpoint does not need to be cleared. A stall on a bulk or interrupt endpoint must be cleared by calling `clearHalt()` before `transferIn()` can be called again.
-   `"babble"` - The device responded with more data than was expected.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#usbintransferresult">WebUSB<br />
<span class="small">The definition of 'USBInTransferResult' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`USBInTransferResult`

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

`USBInTransferResult`

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

`data`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBInTransferResult" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBInTransferResult</a>
