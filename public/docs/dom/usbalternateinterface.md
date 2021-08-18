USBAlternateInterface
=====================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `USBAlternateInterface` interface of the [WebUSB API](webusb_api) provides information about a particular configuration of an interface provided by the USB device. An interface includes one or more alternate settings which can configure a set of endpoints based on the operating mode of the device.

Constructor
-----------

<span class="page-not-created">`USBAlternateInterface.USBAlternateInterface`</span>  
Creates a new `USBAlternateInterface` object which will be populated with information about the alternate interface of the provided `USBInterface` with the given alternate setting number.

Properties
----------

 <span class="page-not-created">`USBAlternateInterface.alternateSetting`</span><span class="badge inline readonly">Read only </span>   
Returns the alternate setting number of this interface. This is equal to the `bAlternateSetting` field of the interface descriptor defining this interface.

 <span class="page-not-created">`USBAlternateInterface.interfaceClass`</span><span class="badge inline readonly">Read only </span>   
Returns the class of this interface. This is equal to the `bInterfaceClass` field of the interface descriptor defining this interface. [Standardized values](https://www.usb.org/defined-class-codes) for this field are defined by the USB Implementers Forum. A value of `0xFF` indicates a vendor-defined interface.

 <span class="page-not-created">`USBAlternateInterface.interfaceSubclass`</span><span class="badge inline readonly">Read only </span>   
Returns the subclass of this interface. This is equal to the `bInterfaceSubClass` field of the interface descriptor defining this interface. The meaning of this value depends on the `interfaceClass` field.

 <span class="page-not-created">`USBAlternateInterface.interfaceProtocol`</span><span class="badge inline readonly">Read only </span>   
Returns the protocol supported by this interface. This is equal to the `bInterfaceProtocol` field of the interface descriptor defining this interface. The meaning of this value depends on the `interfaceClass` and `interfaceSubclass` fields.

 <span class="page-not-created">`USBAlternateInterface.interfaceName`</span><span class="badge inline readonly">Read only </span>   
Returns the name of the interface, if one is provided by the device. This is the value of the string descriptor with the index specified by the `iInterface` field of the interface descriptor defining this interface.

 <span class="page-not-created">`USBAlternateInterface.endpoints`</span><span class="badge inline readonly">Read only </span>   
Returns an array containing instances of the `USBEndpoint` interface describing each of the endpoints that are part of this interface.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#usbalternateinterface">WebUSB<br />
<span class="small">The definition of 'USBAlternateInterface' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`USBAlternateInterface`

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

`USBAlternateInterface`

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

`alternateSetting`

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

`endpoints`

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

`interfaceClass`

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

`interfaceName`

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

`interfaceProtocol`

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

`interfaceSubclass`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBAlternateInterface" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBAlternateInterface</a>
