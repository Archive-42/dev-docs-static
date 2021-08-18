# BluetoothRemoteGATTServer

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `BluetoothRemoteGATTServer` interface of the [Web Bluetooth API](web_bluetooth_api) represents a GATT Server on a remote device.

This page describes the W3C Community Group Web Bluetooth API. For the Firefox OS Bluetooth API, see [`BluetoothGattServer` (Firefox OS)](https://developer.mozilla.org/en-US/docs/Archive/B2G_OS/API/BluetoothGattServer).

## Interface

    interface BluetoothRemoteGATTServer {
      readonly attribute BluetoothDevice device;
      readonly attribute boolean connected;

      Promise<BluetoothRemoteGATTServer> connect();
      void disconnect();
      Promise<BluetoothRemoteGATTService> getPrimaryService(BluetoothServiceUUID service);
      Promise<sequence<BluetoothRemoteGATTService>> getPrimaryServices(optional BluetoothServiceUUID service);
    };

## Properties

[`BluetoothRemoteGATTServer.connected`](bluetoothremotegattserver/connected)<span class="badge inline readonly">Read only </span>  
A boolean value that returns true while this script execution environment is connected to `this.device`. It can be false while the user agent is physically connected.

[`BluetoothRemoteGATTServer.device`](bluetoothremotegattserver/device)<span class="badge inline readonly">Read only </span>  
A reference to the [`BluetoothDevice`](bluetoothdevice) running the server.

## Methods

[`BluetoothRemoteGATTServer.connect()`](bluetoothremotegattserver/connect)  
Causes the script execution environment to connect to `this.device`.

[`BluetoothRemoteGATTServer.disconnect()`](bluetoothremotegattserver/disconnect)  
Causes the script execution environment to disconnect from `this.device`.

[`BluetoothRemoteGATTServer.getPrimaryService()`](bluetoothremotegattserver/getprimaryservice)  
Returns a promise to the primary [`BluetoothRemoteGATTService`](bluetoothremotegattservice) offered by the bluetooth device for a specified `BluetoothServiceUUID`.

[`BluetoothRemoteGATTServer.getPrimaryServices()`](bluetoothremotegattserver/getprimaryservices)  
Returns a promise to a list of primary [`BluetoothRemoteGATTService`](bluetoothremotegattservice) objects offered by the bluetooth device for a specified `BluetoothServiceUUID`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webbluetoothcg.github.io/web-bluetooth/#bluetoothremotegattserver">Web Bluetooth<br />
<span class="small">The definition of 'BluetoothRemoteGATTServer' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BluetoothRemoteGATTServer`

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

`connect`

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

`connected`

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

`disconnect`

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

`getPrimaryService`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BluetoothRemoteGATTServer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BluetoothRemoteGATTServer</a>
