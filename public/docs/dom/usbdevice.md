USBDevice
=========

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `USBDevice` interface of the [WebUSB API](webusb_api) provides access to metadata about a paired USB device and methods for controlling it.

Properties
----------

 [`USBDevice.configuration`](usbdevice/configuration) <span class="badge inline readonly">Read only </span>   
A [`USBConfiguration`](usbconfiguration) object for the currently selected interface for a paired USB device.

 [`USBDevice.configurations`](usbdevice/configurations) <span class="badge inline readonly">Read only </span>   
An [`array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of device-specific interfaces for controlling a paired USB device.

 [`USBDevice.deviceClass`](usbdevice/deviceclass) <span class="badge inline readonly">Read only </span>   
One of three properties that identify USB devices for the purpose of loading a USB driver that will work with that device. The other two properties are `USBDevice.deviceSubclass` and `USBDevice.deviceProtocol`.

 [`USBDevice.deviceProtocol`](usbdevice/deviceprotocol) <span class="badge inline readonly">Read only </span>   
One of three properties that identify USB devices for the purpose of loading a USB driver that will work with that device. The other two properties are `USBDevice.deviceClass` and `USBDevice.deviceSubclass`.

 [`USBDevice.deviceSubclass`](usbdevice/devicesubclass) <span class="badge inline readonly">Read only </span>   
One of three properties that identify USB devices for the purpose of loading a USB driver that will work with that device. The other two properties are `USBDevice.deviceClass` and `USBDevice.deviceProtocol`.

 [`USBDevice.deviceVersionMajor`](usbdevice/deviceversionmajor) <span class="badge inline readonly">Read only </span>   
The major version number of the device in a semantic versioning scheme.

 [`USBDevice.deviceVersionMinor`](usbdevice/deviceversionminor) <span class="badge inline readonly">Read only </span>   
The minor version number of the device in a semantic versioning scheme.

 [`USBDevice.deviceVersionSubminor`](usbdevice/deviceversionsubminor) <span class="badge inline readonly">Read only </span>   
The patch version number of the device in a semantic versioning scheme.

 [`USBDevice.manufacturerName`](usbdevice/manufacturername) <span class="badge inline readonly">Read only </span>   
The of the organization that manufactured the USB device.

 [`USBDevice.opened`](usbdevice/opened) <span class="badge inline readonly">Read only </span>   
Indicates whether a session has been started with a paired USB device.

 [`USBDevice.productId`](usbdevice/productid) <span class="badge inline readonly">Read only </span>   
The manufacturer-defined code that identifies a USB device.

 [`USBDevice.productName`](usbdevice/productname) <span class="badge inline readonly">Read only </span>   
The manufacturer-defined name that identifies a USB device.

 [`USBDevice.serialNumber`](usbdevice/serialnumber) <span class="badge inline readonly">Read only </span>   
The manufacturer-defined serial number for the specific USB device.

 [`USBDevice.usbVersionMajor`](usbdevice/usbversionmajor) <span class="badge inline readonly">Read only </span>   
One of three properties that declare the USB protocol version supported by the device. The other two properties are `USBDevice.usbVersionMinor` and `USBDevice.usbVersionSubminor`.

 [`USBDevice.usbVersionMinor`](usbdevice/usbversionminor) <span class="badge inline readonly">Read only </span>   
One of three properties that declare the USB protocol version supported by the device. The other two properties are `USBDevice.usbVersionMajor` and `USBDevice.usbVersionSubminor`.

 [`USBDevice.usbVersionSubminor`](usbdevice/usbversionsubminor) <span class="badge inline readonly">Read only </span>   
One of three properties that declare the USB protocol version supported by the device. The other two properties are `USBDevice.usbVersionMajor` and `USBDevice.usbVersionMinor`.

 [`USBDevice.vendorId`](usbdevice/vendorid) <span class="badge inline readonly">Read only </span>   
The official usg.org-assigned vendor ID.

Methods
-------

[`USBDevice.claimInterface()`](usbdevice/claiminterface)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the requested interface is claimed for exclusive access.

[`USBDevice.clearHalt()`](usbdevice/clearhalt)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when a halt condition is cleared.

[`USBDevice.controlTransferIn()`](usbdevice/controltransferin)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a <span class="page-not-created">`USBTransferInResult`</span> when a command or status operation has been transmitted to the USB device.

[`USBDevice.controlTransferOut()`](usbdevice/controltransferout)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a <span class="page-not-created">`USBTransferOutResult`</span> when a command or status operation has been transmitted from the USB device.

[`USBDevice.close()`](usbdevice/close)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when all open interfaces are released and the device session has ended.

[`USBDevice.isochronousTransferIn()`](usbdevice/isochronoustransferin)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`USBIsochronousInTransferResult`](usbisochronousintransferresult) when time sensitive information has been transmitted to the USB device.

[`USBDevice.isochronousTransferOut()`](usbdevice/isochronoustransferout)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`USBIsochronousOutTransferResult`](usbisochronousouttransferresult) when time sensitive information has been transmitted from the USB device.

[`USBDevice.open()`](usbdevice/open)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when a device session has started.

[`USBDevice.releaseInterface()`](usbdevice/releaseinterface)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when a cliamed interface is released from exclusive access.

[`USBDevice.reset()`](usbdevice/reset)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the device is reset and all app operations canceled and their promises rejected.

[`USBDevice.selectAlternateInterface()`](usbdevice/selectalternateinterface)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the specified alternative endpoint is selected.

[`USBDevice.selectConfiguration()`](usbdevice/selectconfiguration)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the specified configuration is selected.

[`USBDevice.transferIn()`](usbdevice/transferin)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a <span class="page-not-created">`USBTransferInResult`</span> when bulk or interrupt data is received from the USB device.

[`USBDevice.transferOut()`](usbdevice/transferout)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a <span class="page-not-created">`USBTransferOutResult`</span> when bulk or interrupt data is sent to the USB device.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#device-usage">WebUSB<br />
<span class="small">The definition of 'USBDevice' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`USBDevice`

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

`clearHalt`

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

`close`

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

`configurations`

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

`controlTransferIn`

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

`controlTransferOut`

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

`deviceClass`

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

`deviceProtocol`

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

`deviceSubclass`

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

`deviceVersionMajor`

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

`deviceVersionMinor`

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

`deviceVersionSubminor`

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

`isochronousTransferIn`

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

`isochronousTransferOut`

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

`manufacturerName`

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

`open`

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

`opened`

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

`productId`

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

`productName`

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

`releaseInterface`

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

`reset`

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

`selectConfiguration`

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

`serialNumber`

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

`transferIn`

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

`transferOut`

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

`usbVersionMajor`

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

`usbVersionMinor`

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

`usbVersionSubminor`

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

`vendorId`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBDevice" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBDevice</a>
