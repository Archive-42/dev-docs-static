USBIsochronousInTransferPacket
==============================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `USBIsochronousInTransferPacket` interface of the [WebUSB API](webusb_api) is part of the response from a call to the `isochronousTransferIn()` method of the `USBDevice` interface. It represents the status of an individual packet from a request to transfer data from the USB device to the USB host over an isochronous endpoint.

Constructor
-----------

<span class="page-not-created">`USBIsochronousInTransferPacket.USBIsochronousInTransferPacket()`</span>  
Creates a new `USBIsochronousInTransferPacket` object with the provided `status` and `data` fields.

Properties
----------

 <span class="page-not-created">`USBIsochronousInTransferPacket.data`</span><span class="badge inline readonly">Read only </span><span class="badge inline readonly">Read only </span>   
Returns a `DataView` object containing the data received from the USB device in this packet, if any.

 <span class="page-not-created">`USBIsochronousInTransferPacket.status`</span><span class="badge inline readonly">Read only </span><span class="badge inline readonly">Read only </span>   
Returns the status of the transfer request, one of:

-   `"ok"` - The transfer was successful.
-   `"stall"` - The device indicated an error by generating a stall condition on the endpoint. A stall on an isochronous endpoint does not need to be cleared.
-   `"babble"` - The device responded with more data than was expected.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#usbisochronousintransferpacket">WebUSB<br />
<span class="small">The definition of 'USBIsochronousInTransferPacket' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`USBIsochronousInTransferPacket`

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

`USBIsochronousInTransferPacket`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBIsochronousInTransferPacket" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBIsochronousInTransferPacket</a>
