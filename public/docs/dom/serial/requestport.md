Serial.requestPort()
====================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `Serial.requestPort()` method of the [`Serial`](../serial) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an instance of [`SerialPort`](../serialport) representing the device chosen by the user or rejects if no device was selected.

Syntax
------

    var promise = Serial.requestPort([options]);

### Parameters

options  
`filters`  
A list of objects containing vendor and product IDs used to search for attached devices. The [USB Implementors Forum](https://www.usb.org/) assigns IDs to specific companies. Each company assigns IDS to it's products. Filters contain the following values:

-   `usbVendorId`: An unsigned short integer that identifies a USB device vendor.
-   `usbProductId`: An unsigned short integer that identiffies a USB device.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an instance of [`SerialPort`](../serialport).

### Exceptions

 [`DOMException`](../domexception) `"SecurityError"`   
The returned `Promise` rejects with this error if a [Feature Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy) restricts use of this API or a permission to use it has not granted via a user gesture.

 [`DOMException`](../domexception) `"AbortError"`   
The returned `Promise` rejects with this if the user does not select a port when prompted.

Examples
--------

The following example shows a filter being passed to `requestPort()` with a USB vendor ID in order to limit the set of devices shown to the user to only USB devices built by a particular manufacturer. If this filter was omitted the user would be able to select any available port.

    button.addEventListener('click', () => {
      const usbVendorId = ...;
      navigator.serial.requestPort({ filters: [{ usbVendorId }]}).then((port) => {
        // Connect to `port` or add it to the list of available ports.
      }).catch((e) => {
        // The user didn't select a port.
      });
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/serial/#dom-serial-requestport">Web Serial API<br />
<span class="small">The definition of 'Serial.requestPort()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`requestPort`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Serial/requestPort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Serial/requestPort</a>
