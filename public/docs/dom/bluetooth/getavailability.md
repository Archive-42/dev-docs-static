# Bluetooth.getAvailability()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `getAvailability()` method of [`Bluetooth`](../bluetooth) interface of [Web Bluetooth API](../web_bluetooth_api) interface exposes the Bluetooth capabilities of the current device. For a returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which is `true` if the device has a Bluetooth adapter and false otherwise (unless user configured [User Agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) not to expose a real value).

**Note:** User might not allow use of Web Bluetooth API, even if `getAvailability()` returned `true` ([`navigator.bluetooth.requestDevice()`](requestdevice) might not resolve with a [`BluetoothDevice`](../bluetoothdevice)). Also, user can configure User Agent to return a fixed value instead of a real one.

## Syntax

    var readerPromise = Bluetooth.getAvailability();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

## Exceptions

This method doesn't throw any exceptions.

## Examples

The following snippet prints out a message in the console specifying whether or not Bluetooth is supported:

    navigator.bluetooth.getAvailability().then(available => {
      if (available)
          console.log("This device supports Bluetooth!");
      else
          console.log("Doh! Bluetooth is not supported");
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webbluetoothcg.github.io/web-bluetooth/#dom-bluetooth-getavailability">Web Bluetooth<br />
<span class="small">The definition of 'getAvailability()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Bluetooth/getAvailability" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Bluetooth/getAvailability</a>
