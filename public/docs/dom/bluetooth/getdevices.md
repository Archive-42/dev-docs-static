# Bluetooth.getDevices()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `getDevices()` method of [`Bluetooth`](../bluetooth) interface of [Web Bluetooth API](../web_bluetooth_api) exposes the Bluetooth devices this origin is allowed to access. This method does not display any permission prompts.

**Note:** This method returns a [`BluetoothDevice`](../bluetoothdevice) for each device the origin is currently allowed to access, even the ones that are out of range or powered off. The program can detect when a device comes online or into range by watching for BlueTooth advertisements by calling <span class="page-not-created">`BluetoothDevice.watchAdvertisements()`</span> on that device.

## Syntax

    var readerPromise = Bluetooth.getDevices();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an array of [`BluetoothDevice`](../bluetoothdevice)s.

## Exceptions

This method doesn't throw any exceptions.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webbluetoothcg.github.io/web-bluetooth/#dom-bluetooth-getdevices">Web Bluetooth<br />
<span class="small">The definition of 'getDevices()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Bluetooth/getDevices" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Bluetooth/getDevices</a>
