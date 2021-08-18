USBIsochronousOutTransferResult
===============================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `USBIsochronousOutTransferResult` interface of the [WebUSB API](webusb_api) provides the result from a call to the `isochronousTransferOut()` method of the `USBDevice` interface. It represents the result from requesting a transfer of data from the USB host to the USB device.

Constructor
-----------

<span class="page-not-created">`USBIsochronousOutTransferResult.USBIsochronousOutTransferResult()`</span>  
Creates a new `USBIsochronousOutTransferResult` object with the provided `packet` field.

Properties
----------

 <span class="page-not-created">`USBIsochronousOutTransferResult.packets`</span><span class="badge inline readonly">Read only </span>   
Returns an array of `USBIsochronousOutTransferPacket` objects containing the result of each request to send a packet to the device.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#usbisochronousouttransferresult">WebUSB<br />
<span class="small">The definition of 'USBIsochronousOutTransferResult' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`USBIsochronousOutTransferResult`

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

`USBIsochronousOutTransferResult`

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

`packets`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBIsochronousOutTransferResult" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBIsochronousOutTransferResult</a>
