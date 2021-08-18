USBIsochronousOutTransferPacket
===============================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `USBIsochronousOutTransferPacket` interface of the [WebUSB API](webusb_api) is part of the response from a call to the `isochronousTransferOut()` method of the `USBDevice` interface. It represents the status of an individual packet from a request to transfer data from the USB host to the USB device over an isochronous endpoint.

Constructor
-----------

<span class="page-not-created">`USBIsochronousOutTransferPacket.USBIsochronousOutTransferPacket()`</span>  
Creates a new `USBIsochronousOutTransferPacket` object with the provided `status` and `bytesWritten` fields.

Properties
----------

 <span class="page-not-created">`USBIsochronousOutTransferPacket.bytesWritten`</span><span class="badge inline readonly">Read only </span>   
Returns the number of bytes from the packet that were sent to the device.

 <span class="page-not-created">`USBIsochronousOutTransferPacket.status`</span><span class="badge inline readonly">Read only </span>   
Returns the status of the transfer request, one of:

-   `"ok"` - The transfer was successful.
-   `"stall"` - The device indicated an error by generating a stall condition on the endpoint. A stall on an isochronous endpoint does not need to be cleared.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#usbisochronousouttransferpacket">WebUSB<br />
<span class="small">The definition of 'USBIsochronousOutTransferPacket' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`USBIsochronousOutTransferPacket`

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

`USBIsochronousOutTransferPacket`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBIsochronousOutTransferPacket" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBIsochronousOutTransferPacket</a>
