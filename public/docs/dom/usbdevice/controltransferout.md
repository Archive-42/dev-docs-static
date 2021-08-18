USBDevice.controlTransferOut()
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `controlTransferOut()` method of the [`USBDevice`](../usbdevice) interface returns a [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`USBOutTransferResult`](../usbouttransferresult) when a command or status operation has been transmitted to the USB device.

Syntax
------

    var promise = USBDevice.controlTransferOut(setup, data)

### Parameters

setup  
An object that sets options for . The available options are:

-   `requestType`: Must be one of three values specifying whether the tranfer is `"standard"` (common to all USB devices) `"class"` (common to an industry-standard class of devices) or `"vendor"`.
-   `recipient`: Specifices the target of the transfer on the device, one of `"device"`, `"interface"`, `"endpoint"`, or `"other"`.
-   `request`: A vendor-specific command.
-   `value`: Vender-specific request parameters.
-   `index`: The interface number of the recipient.

data  
A <span class="page-not-created">`TypedArray`</span> containing the data that will be transfered to the device. Not all commands require data; some commands can send data just through the value parameter. Check with your device to see what the specific request requires.

### Return value

A [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`USBOutTransferResult`](../usbouttransferresult).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#dom-usbdevice-controltransferout">WebUSB<br />
<span class="small">The definition of 'controlTransferOut()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`controlTransferOut`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/controlTransferOut" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/controlTransferOut</a>
