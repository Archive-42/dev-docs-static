USB
===

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `USB` interface of the [WebUSB API](webusb_api) provides attributes and methods for finding and connecting USB devices from a web page.

Properties
----------

None.

### Event handlers

[`USB.onconnect`](usb/onconnect)  
An event handler called whenever a previously paired device is connected.

[`USB.ondisconnect`](usb/ondisconnect)  
An event handler called whenever a paired device is disconnected.

Methods
-------

[`USB.getDevices()`](usb/getdevices)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an array of [`USBDevice`](usbdevice) objects for paired attached devices.

[`USB.requestDevice()`](usb/requestdevice)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an instance of [`USBDevice`](usbdevice) if the specified device is found. Calling this function triggers the user agent's pairing flow.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#enumeration">WebUSB<br />
<span class="small">The definition of 'USB' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`USB`

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

`getDevices`

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

`onconnect`

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

`ondisconnect`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USB" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USB</a>
