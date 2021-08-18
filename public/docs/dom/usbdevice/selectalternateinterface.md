USBDevice.selectAlternateInterface()
====================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `selectAlternateInterface()` method of the [`USBDevice`](../usbdevice) interface returns a [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the specified alternative endpoint is selected.

Syntax
------

    var promise = USBDevice.selectAlternateInterface(interfaceNumber, alternateSetting)

### Parameters

interfaceNumber  
The index of one of the interfaces supported by the device. Interfaces are device-specific.

alternateSetting  
The configuration of the selected interface.

### Return value

A [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#dom-usbdevice-selectalternateinterface">WebUSB<br />
<span class="small">The definition of 'selectAlternateInterface()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`selectAlternateInterface`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/selectAlternateInterface" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/selectAlternateInterface</a>
