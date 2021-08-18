Web Bluetooth API
=================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The Web Bluetooth API provides the ability to connect and interact with Bluetooth Low Energy peripherals.

**Note:** This API is *not available* in [Web Workers](web_workers_api) (not exposed via [`WorkerNavigator`](workernavigator)).

Interfaces
----------

[`Bluetooth`](bluetooth)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to a [`BluetoothDevice`](bluetoothdevice) object with the specified options.

 [`BluetoothAdvertisingData`](bluetoothadvertisingdata) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Provides advertising data about a particular Bluetooth device.

[`BluetoothCharacteristicProperties`](bluetoothcharacteristicproperties)  
Provides properties of a particular `BluetoothRemoteGATTCharacteristic`.

[`BluetoothDevice`](bluetoothdevice)  
Represents a Bluetooth device inside a particular script execution environment.

[`BluetoothRemoteGATTCharacteristic`](bluetoothremotegattcharacteristic)  
Represents a GATT Characteristic, which is a basic data element that provides further information about a peripheral’s service.

[`BluetoothRemoteGATTDescriptor`](bluetoothremotegattdescriptor)  
Represents a GATT Descriptor, which provides further information about a characteristic’s value.

[`BluetoothRemoteGATTServer`](bluetoothremotegattserver)  
Represents a GATT Server on a remote device.

[`BluetoothRemoteGATTService`](bluetoothremotegattservice)  
Represents a service provided by a GATT server, including a device, a list of referenced services, and a list of the characteristics of this service.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Feedback</th></tr></thead><tbody><tr class="odd"><td><a href="https://webbluetoothcg.github.io/web-bluetooth/">Web Bluetooth</a></td><td>To provide feedback on the Web Bluetooth API, <a href="https://github.com/WebBluetoothCG/web-bluetooth/issues/">file a spec issue</a>.</td></tr></tbody></table>

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

`Web_Bluetooth_API`

56

macOS only.

56

Linux and versions of Windows earlier than 10.

70

Windows 10.

79

macOS only.

79

Linux and versions of Windows earlier than 10.

79

Windows 10.

No

No

43

macOS only.

43

Linux and versions of Windows earlier than 10.

57

Windows 10.

No

No

56

No

43

No

6.0

`getAvailability`

56

macOS only.

56

Linux and versions of Windows earlier than 10.

70

Windows 10.

79

macOS only.

79

Linux and versions of Windows earlier than 10.

79

Windows 10.

No

No

43

macOS only.

43

Linux and versions of Windows earlier than 10.

57

Windows 10.

No

No

56

No

43

No

6.0

`getDevices`

85

85

No

No

71

No

No

85

No

No

No

No

`onavailabilitychanged`

56

macOS only.

56

Linux and versions of Windows earlier than 10.

70

Windows 10.

79

macOS only.

79

Linux and versions of Windows earlier than 10.

79

Windows 10.

No

No

43

macOS only.

43

Linux and versions of Windows earlier than 10.

57

Windows 10.

No

No

56

No

43

No

6.0

`referringDevice`

56

macOS only.

56

Linux and versions of Windows earlier than 10.

70

Windows 10.

79

macOS only.

79

Linux and versions of Windows earlier than 10.

79

Windows 10.

No

No

43

macOS only.

43

Linux and versions of Windows earlier than 10.

57

Windows 10.

No

No

56

No

43

No

6.0

`requestDevice`

56

macOS only.

56

Linux and versions of Windows earlier than 10.

70

Windows 10.

79

macOS only.

79

Linux and versions of Windows earlier than 10.

79

Windows 10.

No

No

43

macOS only.

43

Linux and versions of Windows earlier than 10.

57

Windows 10.

No

No

56

No

43

No

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Bluetooth_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Bluetooth_API</a>
