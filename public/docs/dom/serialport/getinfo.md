SerialPort.getInfo()
====================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `SerialPort.getInfo()` method of the [`SerialPort`](../serialport) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an object containing properties of the port.

Syntax
------

    var promise = SerialPort.getInfo();

### Parameters

None.

### Return value

An object containing the following values.

`usbVendorId`  
If the port is part of a USB device, an unsigned short integer that identifies a USB device vendor, otherwise `undefined`.

`usbProductId`  
If the port is part of a USB device, an unsigned short integer that identiffies a USB device, otherwise `undefined`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/serial/#dom-serialport-getinfo">Web Serial API<br />
<span class="small">The definition of 'SerialPort.getInfo()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getInfo`

89

89

No

No

No

No

No

No

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SerialPort/getInfo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SerialPort/getInfo</a>
