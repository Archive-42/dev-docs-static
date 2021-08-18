USBDevice.transferIn()
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `transferIn()` method of the [`USBDevice`](../usbdevice) interface returns a [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a <span class="page-not-created">`USBTransferInResult`</span> when bulk or interrupt data is received from the USB device.

Syntax
------

    var promise = USBDevice.transferIn(endpointNumber, length)

### Parameters

endpointNumber  
The number of a device-specific endpoint (buffer).

length  
The maximum number of bytes that will be read back from the device. The actual data is in the [`USBInTransferResult`](../usbintransferresult) in the resolved Promise.

### Return value

A [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a <span class="page-not-created">`USBTransferInResult`</span>.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#dom-usbdevice-transferin">WebUSB<br />
<span class="small">The definition of 'transferIn()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`transferIn`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/transferIn" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/transferIn</a>
