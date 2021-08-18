# BluetoothRemoteGATTService

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

This page describes the W3C Community Group BluetoothRemoteGATTService, formerly called BluethoothGATTService. For the Firefox OS interface of the same name, see `BluetoothGattService`.

The `BluetoothRemoteGATTService` interface of the [Web Bluetooth API](web_bluetooth_api) represents a service provided by a GATT server, including a device, a list of referenced services, and a list of the characteristics of this service.

## Interface

    interface BluetoothRemoteGATTService : ServiceEventHandlers {
      readonly attribute UUID uuid;
      readonly attribute boolean isPrimary;
      readonly attribute BluetoothDevice device;
      Promise<BluetoothGATTCharacteristic> getCharacteristic(BluetoothCharacteristicUUID characteristic);
      Promise<sequence<BluetoothGATTCharacteristic>> getCharacteristics(optional BluetoothCharacteristicUUID characteristic);
      Promise<BluetoothGATTService> getIncludedService(BluetoothServiceUUID service);
      Promise<sequence<BluetoothGATTService>> getIncludedServices(optional BluetoothServiceUUID service);
    };

## Properties

[`BluetoothRemoteGATTService.device`](bluetoothremotegattservice/device)<span class="badge inline readonly">Read only </span>  
Returns information about a Bluetooth device through an instance of [`BluetoothDevice`](bluetoothdevice).

[`BluetoothRemoteGATTService.isPrimary`](bluetoothremotegattservice/isprimary)<span class="badge inline readonly">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) Indicating whether this is a primary or secondary service.

[`BluetoothRemoteGATTService.uuid`](bluetoothremotegattservice/uuid)<span class="badge inline readonly">Read only </span>  
Returns a [`DOMString`](domstring) representing the UUID of this service.

## Methods

[`BluetoothRemoteGATTService.getCharacteristic()`](bluetoothremotegattservice/getcharacteristic)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to an instance of [`BluetoothRemoteGATTCharacteristic`](bluetoothremotegattcharacteristic) for a given universally unique identifier (UUID).

[`BluetoothRemoteGATTService.getCharacteristics()`](bluetoothremotegattservice/getcharacteristics)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to an <span class="page-not-created">`Array`</span> of [`BluetoothRemoteGATTCharacteristic`](bluetoothremotegattcharacteristic) instances for an optional universally unique identifier (UUID).

[`BluetoothRemoteGATTService.getIncludedService()`](bluetoothremotegattservice/getincludedservice)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to an instance of [`BluetoothRemoteGATTService`](bluetoothremotegattservice) for a given universally unique identifier (UUID).

[`BluetoothRemoteGATTService.getIncludedServices()`](bluetoothremotegattservice/getincludedservices)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to an <span class="page-not-created">`Array`</span> of [`BluetoothRemoteGATTService`](bluetoothremotegattservice) instances for an optional universally unique identifier (UUID).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webbluetoothcg.github.io/web-bluetooth/#bluetoothremotegattservice">Web Bluetooth<br />
<span class="small">The definition of 'BluetoothRemoteGATTService' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BluetoothRemoteGATTService`

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

`device`

No

No

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

No

No

43

No

No

`getCharacteristic`

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

`getCharacteristics`

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

`getIncludedService`

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

`getIncludedServices`

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

`isPrimary`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BluetoothRemoteGATTService" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BluetoothRemoteGATTService</a>
