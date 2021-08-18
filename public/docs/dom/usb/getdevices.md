USB.getDevices()
================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `getDevices` method of the [`USB`](../usb) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an array of [`USBDevice`](../usbdevice) objects for paired attached devices. For information on pairing devices, see [`USB.requestDevice()`](requestdevice).

Syntax
------

    USB.getDevices()

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an array of [`USBDevice`](../usbdevice) objects.

Example
-------

The following example logs the product name and serial number of paired devices to the console. For information on pairing devices, see [`USB.requestDevice()`](requestdevice).

    navigator.usb.getDevices()
    .then(devices => {
      console.log("Total devices: " + devices.length);
      devices.forEach(device => {
        console.log("Product name: " + device.productName + ", serial number " + device.serialNumber);
      });
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#dom-usb-getdevices">WebUSB<br />
<span class="small">The definition of 'getDevices' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getDevices`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USB/getDevices" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USB/getDevices</a>
