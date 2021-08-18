USBIsochronousInTransferResult
==============================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `USBIsochronousInTransferResult` interface of the [WebUSB API](webusb_api) provides the result from a call to the `isochronousTransferIn()` method of the `USBDevice` interface. It represents the result from requesting a transfer of data from the USB device to the USB host.

Constructor
-----------

<span class="page-not-created">`USBIsochronousInTransferResult.USBIsochronousInTransferResult()`</span>  
Creates a new `USBIsochronousInTransferResult` object with the provided `packets` and `data` fields.

Properties
----------

 <span class="page-not-created">`USBIsochronousInTransferResult.data`</span><span class="badge inline readonly">Read only </span>   
Returns a `DataView` object containing the data received from the device. This is the combined data from all packets. See the individual `DataView` objects in the `packets` array for the portion of this buffer containing data from each packet.

 <span class="page-not-created">`USBIsochronousInTransferResult.packets`</span><span class="badge inline readonly">Read only </span>   
Returns an array of `USBIsochronousInTransferPacket` objects containing the result of each request to receive a packet from the device.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#usbisochronousintransferresult">WebUSB<br />
<span class="small">The definition of 'USBIsochronousInTransferResult' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`USBIsochronousInTransferResult`

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

`USBIsochronousInTransferResult`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBIsochronousInTransferResult" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBIsochronousInTransferResult</a>
