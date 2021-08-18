USBDevice.claimInterface()
==========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `claimInterface()` method of the [`USBDevice`](../usbdevice) interface returns a [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the requested interface is claimed for exclusive access.

Syntax
------

    var promise = USBDevice.claimInterface(interfaceNumber)

### Parameters

interfaceNumber  
The index of one of the interfaces supported by the device. Interfaces are device-specific.

### Return value

A [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

Example
-------

The following example shows `claimInterface()` in the context of connecting to a USB device.

    async function connectDevice(usbDevice) {
      await usbDevice.open();
      if (usbDevice.configuration === null)
        await usbDevice.selectConfiguration(1);
      await usbDevice.claimInterface(0);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#dom-usbdevice-claiminterface">WebUSB<br />
<span class="small">The definition of 'claimInterface()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`claimInterface`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/claimInterface" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/claimInterface</a>
