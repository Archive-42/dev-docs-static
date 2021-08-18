USBInterface
============

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `USBInterface` interface of the [WebUSB API](webusb_api) provides information about an interface provided by the USB device. An interface represents a feature of the device which implements a particular protocol and may contain endpoints for bidirectional communication.

Constructor
-----------

<span class="page-not-created">`USBInterface.USBInterface`</span>  
Creates a new `USBInterface` object which will be populated with information about the interface on the provided `USBConfiguration` with the given interface number.

Properties
----------

 <span class="page-not-created">`USBInterface.interfaceNumber`</span><span class="badge inline readonly">Read only </span>   
Returns the interface number of this interface. This is equal to the `bInterfaceNumber` field of the interface descriptor defining this interface.

 <span class="page-not-created">`USBInterface.alternate`</span><span class="badge inline readonly">Read only </span>   
Returns the currently selected alternative configuration of this interface. By default this is the `USBAlternateInterface` from `alternates` with `alternateSetting` equal to `0`. It can be changed by calling `USBDevice.selectAlternateInterface()` with any other value found in `alternates`.

 <span class="page-not-created">`USBInterface.alternates`</span><span class="badge inline readonly">Read only </span>   
Returns an array containing instances of the `USBAlternateInterface` interface describing each of the alternative configurations possible for this interface.

 **<span class="page-not-created">`USBInterface.claimed`</span>**<span class="badge inline readonly">Read only </span>   
Returns whether or not this interface has been claimed by the current page by calling `USBDevice.claimInterface()`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#usbinterface">WebUSB<br />
<span class="small">The definition of 'USBInterface' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`USBInterface`

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

`USBInterface`

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

`alternate`

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

`alternates`

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

`claimed`

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

`interfaceNumber`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBInterface" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBInterface</a>
