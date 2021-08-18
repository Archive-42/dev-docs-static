# BluetoothRemoteGATTServer.getPrimaryServices()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The **BluetoothRemoteGATTServer.getPrimaryServices()** method returns a promise to a list of primary [`BluetoothRemoteGATTService`](../bluetoothremotegattservice) objects offered by the bluetooth device for a specified `BluetoothServiceUUID`.

## Syntax

    BluetoothRemoteGATTServer.getPrimaryServices(bluetoothServiceUUID).then(function(bluetoothGATTServices) { ... })

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a list of [`BluetoothRemoteGATTService`](../bluetoothremotegattservice) objects.

### Parameters

`BluetoothServiceUUID`  
A Bluetooth service universally unique identifier for a specified device.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webbluetoothcg.github.io/web-bluetooth/#dom-bluetoothremotegattserver-getprimaryservices">Web Bluetooth<br />
<span class="small">The definition of 'getPrimaryServices()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getPrimaryServices`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BluetoothRemoteGATTServer/getPrimaryServices" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BluetoothRemoteGATTServer/getPrimaryServices</a>
