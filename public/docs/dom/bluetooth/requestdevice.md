# Bluetooth.requestDevice()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Bluetooth.requestDevice()` method of the [`Bluetooth`](../bluetooth) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to a [`BluetoothDevice`](../bluetoothdevice) object with the specified options. If there is no chooser UI, this method returns the first device matching the criteria.

## Syntax

    Bluetooth.requestDevice([options])
      .then(function(bluetoothDevice) { ... })

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to a [`BluetoothDevice`](../bluetoothdevice) object.

### Parameters

options <span class="badge inline optional">Optional</span>  
An object that sets options for the device request. The available options are:

- `filters[]`: An array of `BluetoothScanFilters`. This filter consists of an array of `BluetoothServiceUUID`s, a `name` parameter, and a `namePrefix` parameter.
- `optionalServices[]`: An array of `BluetoothServiceUUID`s.
- `acceptAllDevices`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating that the requesting script can accept all Bluetooth devices. The default is `false`.

## Exceptions

`TypeError`  
The provided `options` do not makes sense. For example, `options.filters` is present and `options.acceptAllDevices` is `true`, or if `options.filters` is not present and `options.acceptAllDevices` is `false`. Or `options.filters` is `[]`.

`NotFoundError`  
There is no Bluetooth device that matches the specified options.

`SecurityError`  
This operation is not permitted in this context due to security concerns. For example, it is called from insecure origin.

## Example

    // Discovery options match any devices advertising:
    // . The standard heart rate service.
    // . Both 16-bit service IDs 0x1802 and 0x1803.
    // . A proprietary 128-bit UUID service c48e6067-5295-48d3-8d5c-0395f61792b1.
    // . Devices with name "ExampleName".
    // . Devices with name starting with "Prefix".
    //
    // And enables access to the battery service if devices
    // include it, even if devices do not advertise that service.
    let options = {
      filters: [
        {services: ['heart_rate']},
        {services: [0x1802, 0x1803]},
        {services: ['c48e6067-5295-48d3-8d5c-0395f61792b1']},
        {name: 'ExampleName'},
        {namePrefix: 'Prefix'}
      ],
      optionalServices: ['battery_service']
    }

    navigator.bluetooth.requestDevice(options).then(function(device) {
      console.log('Name: ' + device.name);
      // Do something with the device.
    })
    .catch(function(error) {
      console.log("Something went wrong. " + error);
    });

[Detailed examples](https://webbluetoothcg.github.io/web-bluetooth/#example-filter-by-services) are in the specification.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webbluetoothcg.github.io/web-bluetooth/#dom-bluetooth-requestdevice">Web Bluetooth<br />
<span class="small">The definition of 'requestDevice()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Bluetooth/requestDevice" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Bluetooth/requestDevice</a>
