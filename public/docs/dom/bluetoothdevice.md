# BluetoothDevice

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The BluetoothDevice interface of the [Web Bluetooth API](web_bluetooth_api) represents a Bluetooth device inside a particular script execution environment.

## Interface

    interface BluetoothDevice {
      readonly attribute DOMString id;
      readonly attribute DOMString? name;
      readonly attribute BluetoothRemoteGATTServer? gatt;
      readonly attribute FrozenArray uuids;

      Promise watchAdvertisements();
      void unwatchAdvertisements();
      readonly attribute boolean watchingAdvertisements;
    };
    BluetoothDevice implements EventTarget;
    BluetoothDevice implements BluetoothDeviceEventHandlers;
    BluetoothDevice implements CharacteristicEventHandlers;
    BluetoothDevice implements ServiceEventHandlers;

## Properties

[`BluetoothDevice.id`](bluetoothdevice/id) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) that uniquely identifies a device.

[`BluetoothDevice.name`](bluetoothdevice/name) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) that provices a human-readable name for the device.

[`BluetoothDevice.gatt`](bluetoothdevice/gatt) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>  
A reference to the device's [`BluetoothRemoteGATTServer`](bluetoothremotegattserver).

[`BluetoothDevice.uuids`](bluetoothdevice/uuids) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
Lists the UUID's of GATT services provided by the device, that the current origin is allowed to access.

<span class="page-not-created">`BluetoothDevice.watchingAdvertisements`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>  
If advertisments were activated using <span class="page-not-created">`BluetoothDevice.watchAdvertisements()`</span>.

### Non-standard Chrome OS properties

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

These properties were only implemented on Google’s Chrome OS 45 and removed from Chrome 52.

[`BluetoothDevice.adData`](bluetoothdevice/addata) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
An instance of [`BluetoothAdvertisingData`](bluetoothadvertisingdata) containing the most recent advertising data received for the device.

[`BluetoothDevice.deviceClass`](bluetoothdevice/deviceclass) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
A number representing the Bluetooth devices "Class of Device".

[`BluetoothDevice.vendorIDSource`](bluetoothdevice/vendoridsource) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
The Vendor ID Source field in the `pnp_id` characteristic in the `device_information` service.

[`BluetoothDevice.vendorID`](bluetoothdevice/vendorid) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
The 16-bit Vendor ID field in the `pnp_id` characteristic in the `device_information` service.

[`BluetoothDevice.productID`](bluetoothdevice/productid) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
The 16-bit Product ID field in the `pnp_id` characteristic in the `device_information` service.

[`BluetoothDevice.productVersion`](bluetoothdevice/productversion) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
The 16-bit Product Version field in the `pnp_id` characteristic in the `device_information` service.

[`BluetoothDevice.paired`](bluetoothdevice/paired) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating whether the device is paired with the system.

[`BluetoothDevice.gattServer`](bluetoothdevice/gattserver) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>  
A reference to the device's GATT server or null if the device is disconnected.

## Methods

<span class="page-not-created">`BluetoothDevice.watchAdvertisments()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to `undefined` or is rejected with an error if advetisments can’t shown for any reason.

<span class="page-not-created">`BluetoothDevice.unwatchAdvertisments()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Stops watching for advertisments.

[`BluetoothDevice.connectGATT()`](bluetoothdevice/connectgatt) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an instance of [`BluetoothRemoteGATTServer`](bluetoothremotegattserver).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webbluetoothcg.github.io/web-bluetooth/#bluetoothdevice">Web Bluetooth<br />
<span class="small">The definition of 'BluetoothDevice' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`BluetoothDevice`

74

79

No

No

62

No

No

74

No

53

No

11.0

`adData`

No

No

No

No

No

No

No

No

No

No

No

No

`connectGATT`

No

No

No

No

No

No

No

No

No

No

No

No

`deviceClass`

No

No

No

No

No

No

No

No

No

No

No

No

`gatt`

74

79

No

No

62

No

No

74

No

53

No

11.0

`gattServer`

No

No

No

No

No

No

No

No

No

No

No

No

`id`

74

79

No

No

62

No

No

74

No

53

No

11.0

`name`

74

79

No

No

62

No

No

74

No

53

No

11.0

`paired`

No

No

No

No

No

No

No

No

No

No

No

No

`productID`

No

No

No

No

No

No

No

No

No

No

No

No

`productVersion`

No

No

No

No

No

No

No

No

No

No

No

No

`unwatchAdvertisements`

No

No

No

No

No

No

No

No

No

No

No

No

`uuids`

No

No

No

No

No

No

No

No

No

No

No

No

`vendorID`

No

No

No

No

No

No

No

No

No

No

No

No

`vendorIDSource`

No

No

No

No

No

No

No

No

No

No

No

No

`watchAdvertisements`

No

No

No

No

No

No

No

No

No

No

No

No

`watchingAdvertisements`

No

No

No

No

No

No

No

No

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BluetoothDevice" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BluetoothDevice</a>
