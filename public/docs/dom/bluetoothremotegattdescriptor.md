# BluetoothRemoteGATTDescriptor

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `BluetoothRemoteGATTDescriptor` interface of the [Web Bluetooth API](web_bluetooth_api) provides a GATT Descriptor, which provides further information about a characteristic’s value.

This page describes the W3C Community Group Web Bluetooth API. For the Firefox OS Bluetooth API, see [`BluetoothGattDescriptor` (Firefox OS)](https://developer.mozilla.org/en-US/docs/Archive/B2G_OS/API/BluetoothGattDescriptor).

## Interface

    interface BluetoothRemoteGATTDescriptor {
      readonly attribute BluetoothGATTCharacteristic characteristic;
      readonly attribute UUID uuid;
      readonly attribute ArrayBuffer? value;
      Promise<ArrayBuffer> readValue();
      Promise<void> writeValue(BufferSource value);
    };

## Properties

[`BluetoothRemoteGATTDescriptor.characteristic`](bluetoothremotegattdescriptor/characteristic)<span class="badge inline readonly">Read only </span>  
Returns the [`BluetoothRemoteGATTCharacteristic`](bluetoothremotegattcharacteristic) this descriptor belongs to.

[`BluetoothRemoteGATTDescriptor.uuid`](bluetoothremotegattdescriptor/uuid)<span class="badge inline readonly">Read only </span>  
Returns the UUID of the characteristic descriptor, for example '`00002902-0000-1000-8000-00805f9b34fb`' for theClient Characteristic Configuration descriptor.

[`BluetoothRemoteGATTDescriptor.value`](bluetoothremotegattdescriptor/value)<span class="badge inline readonly">Read only </span>  
Returns the currently cached descriptor value. This value gets updated when the value of the descriptor is read.

## Methods

[`BluetoothRemoteGATTDescriptor.readValue()`](bluetoothremotegattdescriptor/readvalue)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) holding a duplicate of the `value` property if it is available and supported. Otherwise it throws an error.

[`BluetoothRemoteGATTDescriptor.writeValue()`](bluetoothremotegattdescriptor/writevalue)  
Sets the value property to the bytes contained in an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webbluetoothcg.github.io/web-bluetooth/#bluetoothremotegattdescriptor">Web Bluetooth<br />
<span class="small">The definition of 'BluetoothRemoteGATTDescriptor' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BluetoothRemoteGATTDescriptor`

57

macOS only.

57

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

44

macOS only.

44

Linux and versions of Windows earlier than 10.

57

Windows 10.

No

No

57

No

44

No

7.0

`characteristic`

57

macOS only.

57

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

44

macOS only.

44

Linux and versions of Windows earlier than 10.

57

Windows 10.

No

No

57

No

44

No

7.0

`readValue`

57

macOS only.

57

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

44

macOS only.

44

Linux and versions of Windows earlier than 10.

57

Windows 10.

No

No

57

No

44

No

7.0

`uuid`

57

macOS only.

57

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

44

macOS only.

44

Linux and versions of Windows earlier than 10.

57

Windows 10.

No

No

57

No

44

No

7.0

`value`

57

macOS only.

57

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

44

macOS only.

44

Linux and versions of Windows earlier than 10.

57

Windows 10.

No

No

57

No

44

No

7.0

`writeValue`

57

macOS only.

57

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

44

macOS only.

44

Linux and versions of Windows earlier than 10.

57

Windows 10.

No

No

57

No

44

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BluetoothRemoteGATTDescriptor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BluetoothRemoteGATTDescriptor</a>
