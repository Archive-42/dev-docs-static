USBDevice.configuration
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `configuration` read only property of the [`USBDevice`](../usbdevice) interface returns a [`USBConfiguration`](../usbconfiguration) object for the currently selected interface for a paired USB device.

Syntax
------

    var USBConfiguration = USBDevice.configuration

### Value

A [`USBConfiguration`](../usbconfiguration) object.

Example
-------

The following example uses this property to test for the existence of a USBConfiguration property to select a configuration before claiming an interface.

    async function connectDevice(usbDevice) {
      await usbDevice.open();
      if (usbDevice.configuration === null)
        await usbDevice.selectConfiguration(1);
      await usbDevice.claimInterface(0);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#dom-usbdevice-configuration">WebUSB<br />
<span class="small">The definition of 'configuration' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`configuration`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/configuration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/configuration</a>
