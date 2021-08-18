# BluetoothRemoteGATTCharacteristic

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `BluetoothRemoteGattCharacteristic` interface of the [Web Bluetooth API](web_bluetooth_api) represents a GATT Characteristic, which is a basic data element that provides further information about a peripheral’s service.

## Interface

    interface BluetoothRemoteGATTCharacteristic {
      readonly attribute BluetoothRemoteGATTService service;
      readonly attribute UUID uuid;
      readonly attribute BluetoothCharacteristicProperties properties;
      readonly attribute DataView? value;
      Promise<BluetoothRemoteGATTDescriptor> getDescriptor(BluetoothDescriptorUUID descriptor);
      Promise<sequence<BluetoothRemoteGATTDescriptor>>
        getDescriptors(optional BluetoothDescriptorUUID descriptor);
      Promise<DataView> readValue();
      Promise<void> writeValue(BufferSource value);
      Promise<void> startNotifications();
      Promise<void> stopNotifications();
    };
    BluetoothRemoteGATTCharacteristic implements EventTarget;
    BluetoothRemoteGATTCharacteristic implements CharacteristicEventHandlers;

## Properties

[`BluetoothRemoteGATTCharacteristic.service`](bluetoothremotegattcharacteristic/service)<span class="badge inline readonly">Read only </span>  
Returns the [`BluetoothRemoteGATTService`](bluetoothremotegattservice) this characteristic belongs to.

[`BluetoothRemoteGATTCharacteristic.uuid`](bluetoothremotegattcharacteristic/uuid)<span class="badge inline readonly">Read only </span>  
Returns a [`DOMString`](domstring) containing the UUID of the characteristic, for example `'00002a37-0000-1000-8000-00805f9b34fb'` for the Heart Rate Measurement characteristic.

[`BluetoothRemoteGATTCharacteristic.properties`](bluetoothremotegattcharacteristic/properties)<span class="badge inline readonly">Read only </span>  
Returns the properties of this characteristic.

[`BluetoothRemoteGATTCharacteristic.value`](bluetoothremotegattcharacteristic/value)<span class="badge inline readonly">Read only </span>  
The currently cached characteristic value. This value gets updated when the value of the characteristic is read or updated via a notification or indication.

## Methods

[`BluetoothRemoteGATTCharacteristic.getDescriptor()`](bluetoothremotegattcharacteristic/getdescriptor)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the first [`BluetoothRemoteGATTDescriptor`](bluetoothremotegattdescriptor) for a given descriptor UUID.

[`BluetoothRemoteGATTCharacteristic.getDescriptors()`](bluetoothremotegattcharacteristic/getdescriptors)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of all [`BluetoothRemoteGATTDescriptor`](bluetoothremotegattdescriptor) objects for a given descriptor UUID.

[`BluetoothRemoteGATTCharacteristic.readValue()`](bluetoothremotegattcharacteristic/readvalue)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) holding a duplicate of the `value` property if it is available and supported. Otherwise it throws an error.

[`BluetoothRemoteGATTCharacteristic.writeValue()`](bluetoothremotegattcharacteristic/writevalue)  
Sets the value property to the bytes contained in an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

[`BluetoothRemoteGATTCharacteristic.startNotifications()`](bluetoothremotegattcharacteristic/startnotifications)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) when `navigator.bluetooth` is added to the active notification context.

[`BluetoothRemoteGATTCharacteristic.stopNotifications()`](bluetoothremotegattcharacteristic/stopnotifications)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) when `navigator.bluetooth` is removed from the active notification context.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webbluetoothcg.github.io/web-bluetooth/#bluetoothremotegattcharacteristic">Web Bluetooth<br />
<span class="small">The definition of 'BluetoothRemoteGATTCharacteristic' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BluetoothRemoteGATTCharacteristic`

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

85

56

No

43

No

6.0

`getDescriptor`

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

`getDescriptors`

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

`properties`

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

`readValue`

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

`service`

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

`startNotifications`

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

`stopNotifications`

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

`uuid`

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

`value`

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

`writeValue`

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

`writeValueWithoutResponse`

85

85

No

No

71

No

85

85

No

60

No

14.0

`writeValueWithResponse`

85

85

No

No

71

No

85

85

No

60

No

14.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BluetoothRemoteGATTCharacteristic" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BluetoothRemoteGATTCharacteristic</a>
