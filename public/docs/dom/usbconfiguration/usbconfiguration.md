USBConfiguration.USBConfiguration()
===================================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `USBConfiguration()` constructor creates a new [`USBConfiguration`](../usbconfiguration) object which contains information about the configuration on the provided USBDevice with the given configuration value.

Syntax
------

    var USBConfiguration = new USBConfiguration(device, configurationValue)

### Parameters

device  
Specifies the [`USBDevice`](../usbdevice) you want to configure.

configurationValue  
Specifies the [configuration descriptor](https://www.beyondlogic.org/usbnutshell/usb5.shtml#ConfigurationDescriptors) you want to read. This is an unsigned integer in the range 0 to 255.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#dom-usbconfiguration-usbconfiguration">WebUSB<br />
<span class="small">The definition of 'USBConfiguration() constructor' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`USBConfiguration`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBConfiguration/USBConfiguration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBConfiguration/USBConfiguration</a>
