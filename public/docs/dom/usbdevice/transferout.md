USBDevice.transferOut()
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `transferOut()` method of the [`USBDevice`](../usbdevice) interface returns a [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a <span class="page-not-created">`USBTransferOutResult`</span> when bulk or interrupt data is sent to the USB device.

Syntax
------

    var promise = USBDevice.transferOut(endpointNumber, data)

### Parameters

endpointNumber  
The number of a device-specific endpoint (buffer).

data  
A <span class="page-not-created">`TypedArray`</span> containing the data to send to the device.

### Return value

A [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a <span class="page-not-created">`USBTransferOutResult`</span>.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#dom-usbdevice-transferout">WebUSB<br />
<span class="small">The definition of 'transferOut()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`transferOut`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/transferOut" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/transferOut</a>
