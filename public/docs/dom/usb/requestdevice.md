USB.requestDevice()
===================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `requestDevice()` method of the [`USB`](../usb) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an instance of [`USBDevice`](../usbdevice) if the specified device is found. Calling this function triggers the user agent's pairing flow.

Syntax
------

    USB.requestDevice([filters])

### Parameters

filters  
An array of filter objects for possible devices you would like to pair. Each filter object can have the following properties:

-   `vendorId`
-   `productId`
-   `classCode`
-   `subclassCode`
-   `protocolCode`
-   `serialNumber`

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an instance of [`USBDevice`](../usbdevice).

Example
-------

The following example looks for one of two USB devices. Notice that two product IDs are specified. Both are passed to `requestDevice()`. This triggers a user-agent flow that prompts the user to select a device for pairing. Only the selected device is passed to `then()`.

The number of filters does not specifiy the number of devices shown by the user agent. For example, if only a USB device with product ID `0xa800` is found, then only one device will be listed by the user agent. On the other hand if the user agent finds two of the first listed device and one of the second, then all three devices will be listed.

    const filters = [
            {vendorId: 0x1209, productId: 0xa800},
            {vendorId: 0x1209, productId: 0xa850}
          ];
    navigator.usb.requestDevice({filters: filters})
    .then(usbDevice => {
      console.log("Product name: " + usbDevice.productName);
    })
    .catch(e => {
      console.log("There is no device. " + e);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#dom-usb-requestdevice-options-options">WebUSB<br />
<span class="small">The definition of 'requestDevice' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`requestDevice`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USB/requestDevice" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USB/requestDevice</a>
