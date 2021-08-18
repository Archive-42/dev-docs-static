USBConfiguration.configurationName
==================================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `configurationName` read-only property of the [`USBConfiguration`](../usbconfiguration) interface returns the name provided by the device to describe this configuration. This is equal to the value of the string descriptor with the index provided in the [`iConfiguration`](https://www.beyondlogic.org/usbnutshell/usb5.shtml#ConfigurationDescriptors) field of the configuration descriptor defining this configuration.

Syntax
------

      var name = USBConfiguration.configurationName

### Value

The name provided by the device to describe this configuration.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#ref-for-dom-usbconfiguration-configurationname">WebUSB<br />
<span class="small">The definition of 'configurationName' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`configurationName`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBConfiguration/configurationName" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBConfiguration/configurationName</a>
