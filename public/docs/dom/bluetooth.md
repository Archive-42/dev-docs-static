# Bluetooth

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Bluetooth` interface of the [Web Bluetooth API](web_bluetooth_api) returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to a [`BluetoothDevice`](bluetoothdevice) object with the specified options.

## Interface

    interface Bluetooth : EventTarget {
      Promise<boolean> getAvailability();
      attribute EventHandler onavailabilitychanged;
      [SameObject]
      readonly attribute BluetoothDevice? referringDevice;
      Promise<sequence<BluetoothDevice>> getDevices();
      Promise<BluetoothDevice> requestDevice(optional RequestDeviceOptions options = {});
    };
    Bluetooth includes BluetoothDeviceEventHandlers;
    Bluetooth includes CharacteristicEventHandlers;
    Bluetooth includes ServiceEventHandlers;

## Properties

_Inherits properties from its parent [`EventTarget`](eventtarget)._

[`Bluetooth.referringDevice`](bluetooth/referringdevice) <span class="badge inline readonly">Read only </span>  
Returns a reference to the device, if any, from which the user opened the current page. For example, an Eddystone beacon might advertise a URL, which the user agent allows the user to open. A BluetoothDevice representing the beacon would be available through `navigator.bluetooth.referringDevice`.

### Events

[`Bluetooth.onavailabilitychanged`](bluetooth/onavailabilitychanged)  
An event handler that runs when an event of type `availabilitychanged` has fired.

## Methods

[`Bluetooth.getAvailability()`](bluetooth/getavailability)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolved to a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the user-agent has the ability to support Bluetooth. Some user-agents let the user configure an option that affects what is returned by this value. If this option is set, that is the value returned by this method.

[`Bluetooth.getDevices()`](bluetooth/getdevices)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolved to an array of [`BluetoothDevice`](bluetoothdevice)s which the origin already obtained permission for via a call to [`Bluetooth.requestDevice()`](bluetooth/requestdevice).

[`Bluetooth.requestDevice()`](bluetooth/requestdevice)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to a [`BluetoothDevice`](bluetoothdevice) object with the specified options.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webbluetoothcg.github.io/web-bluetooth/#bluetooth">Web Bluetooth<br />
<span class="small">The definition of 'Bluetooth' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Bluetooth`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Bluetooth" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Bluetooth</a>
