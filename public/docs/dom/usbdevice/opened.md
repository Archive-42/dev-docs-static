USBDevice.opened
================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `opened` read only property of the [`USBDevice`](../usbdevice) interface indicates whether a session has been started with a paired USB device. A device must be opened before it can be controlled by a web page.

Syntax
------

    var serialNumber = USBDevice.opened

### Value

A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Example
-------

This example is for a hypothetical USB device with a multi-colored LED. It shows how to test that a device is open before calling [`USBDevice.controlTransferOut`](controltransferout) to set a specified LED color.

What data can be passed to a USB device and how it is passed is particular and unique to each device.

    async setDeviceColor(usbDevice, r, g, b) {
       if (device.opened) {
         // This hypothetical USB device requires that the data passed to
         // it be in a Uint8Array.
         let payload = new Uint8Array([r, g, b]);

         await usbDevice.controlTransferOut({
           requestType: 'vendor',
           recipient: 'device',
           request: 1,
           value: 0,
           index: 0,
         }, payload);
       }
     }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#dom-usbdevice-opened">WebUSB<br />
<span class="small">The definition of 'opened' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`opened`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/opened" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/opened</a>
