USBDevice.controlTransferIn()
=============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `controlTransferIn()` method of the [`USBDevice`](../usbdevice) interface returns a [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`USBInTransferResult`](../usbintransferresult) when the result of a command or status request has been received from the USB device.

Syntax
------

    var promise = USBDevice.controlTransferIn(setup, length)

### Parameters

setup   
An object that sets options for . The available options are:

-   `requestType`: Must be one of three values specifying whether the tranfer is `"standard"` (common to all USB devices) `"class"` (common to an industry-standard class of devices) or `"vendor"`.
-   `recipient`: Specifices the target of the transfer on the device, one of `"device"`, `"interface"`, `"endpoint"`, or `"other"`.
-   `request`: A vendor-specific command.
-   `value`: Vender-specific request parameters.
-   `index`: The interface number of the recipient.

length  
The maximum number of bytes to read from the device. The actual data is in the [`USBInTransferResult`](../usbintransferresult) in the resolved Promise.

### Return value

[`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`USBInTransferResult`](../usbintransferresult).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#dom-usbdevice-controltransferin">WebUSB<br />
<span class="small">The definition of 'controlTransferIn()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`controlTransferIn`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/controlTransferIn" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/controlTransferIn</a>
