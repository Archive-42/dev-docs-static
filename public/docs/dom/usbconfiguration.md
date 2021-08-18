USBConfiguration
================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `USBConfiguration` interface of the [WebUSB API](webusb_api) provides information about a particular configuration of a USB device and the interfaces that it supports.

Constructor
-----------

[`USBConfiguration.USBConfiguration()`](usbconfiguration/usbconfiguration)  
Creates a new `USBConfiguration` object which contains information about the configuration on the provided `USBDevice` with the given configuration value.

Properties
----------

 [`USBConfiguration.configurationValue`](usbconfiguration/configurationvalue)<span class="badge inline readonly">Read only </span>   
Returns the configuration value of this configuration. This is equal to the [`bConfigurationValue`](https://www.beyondlogic.org/usbnutshell/usb5.shtml#ConfigurationDescriptors) field of the configuration descriptor provided by the device defining this configuration.

 [`USBConfiguration.configurationName`](usbconfiguration/configurationname)<span class="badge inline readonly">Read only </span>   
Returns the name provided by the device to describe this configuration. This is equal to the value of the string descriptor with the index provided in the [`iConfiguration`](https://www.beyondlogic.org/usbnutshell/usb5.shtml#ConfigurationDescriptors) field of the configuration descriptor defining this configuration.

 [`USBConfiguration.interfaces`](usbconfiguration/interfaces)<span class="badge inline readonly">Read only </span>   
Returns an array containing instances of the [`USBInterface`](usbinterface) describing each interface supported by this configuration.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#configurations">WebUSB<br />
<span class="small">The definition of 'USBConfiguration' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`configurationValue`

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

`interfaces`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBConfiguration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBConfiguration</a>
