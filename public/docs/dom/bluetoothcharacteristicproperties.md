# BluetoothCharacteristicProperties

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `BluetoothCharacteristicProperties` interface of the [Web Bluetooth API](web_bluetooth_api) provides the operations that are valid on the given [`BluetoothRemoteGATTCharacteristic`](bluetoothremotegattcharacteristic). This interface is returned by calling [`BluetoothRemoteGATTCharacteristic.properties`](bluetoothremotegattcharacteristic/properties).

## Properties

[`authenticatedSignedWrites`](bluetoothcharacteristicproperties/authenticatedsignedwrites)<span class="badge inline readonly">Read only </span>  
Returns a `boolean` that is `true` if signed writing to the characteristic value is permitted.

[`broadcast`](bluetoothcharacteristicproperties/broadcast)<span class="badge inline readonly">Read only </span>  
Returns a `boolean` that is `true` if the broadcast of the characteristic value is permitted using the Server Characteristic Configuration Descriptor.

[`indicate`](bluetoothcharacteristicproperties/indicate)<span class="badge inline readonly">Read only </span>  
Returns a `boolean` that is `true` if indications of the characteristic value with acknowledgement is permitted.

[`notify`](bluetoothcharacteristicproperties/notify)<span class="badge inline readonly">Read only </span>  
Returns a `boolean` that is `true` if notifications of the characteristic value without acknowledgement is permitted.

[`read`](bluetoothcharacteristicproperties/read)<span class="badge inline readonly">Read only </span>  
Returns a `boolean` that is `true` if the reading of the characteristic value is permitted.

[`reliableWrite`](bluetoothcharacteristicproperties/reliablewrite)<span class="badge inline readonly">Read only </span>  
Returns a `boolean` that is `true` if reliable writes to the characteristic is permitted.

<span class="page-not-created">`writableAuxiliaries`</span><span class="badge inline readonly">Read only </span>  
Returns a `boolean` that is `true` if reliable writes to the characteristic descriptor is permitted.

[`write`](bluetoothcharacteristicproperties/write)<span class="badge inline readonly">Read only </span>  
Returns a `boolean` that is `true` if the writing to the characteristic with response is permitted.

<span class="page-not-created">`writeWithoutResponse`</span><span class="badge inline readonly">Read only </span>  
Returns a `boolean` that is `true` if the writing to the characteristic without response is permitted.

## Examples

The following example shows how tell if a GATT characteristic supports value change notifications.

    let device = await navigator.bluetooth.requestDevice({
      filters: [{services: ['heart_rate']}]
    });
    let gatt = await device.gatt.connect();
    let service = await gatt.getPrimaryService('heart_rate');
    let characteristic = await service.getCharacteristic('heart_rate_measurement');
    if (characteristic.properties.notify) {
      characteristic.addEventListener('characteristicvaluechanged',
          function(event) {
        console.log(`Received heart rate measurement: ${event.target.value}`);
      }
      await characteristic.startNotifications();
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webbluetoothcg.github.io/web-bluetooth/#characteristicproperties-interface">Web Bluetooth<br />
<span class="small">The definition of 'BluetoothCharacteristicProperties' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BluetoothCharacteristicProperties`

56

ChromeOS and macOS only.

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

`authenticatedSignedWrites`

56

ChromeOS and macOS only.

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

`broadcast`

56

ChromeOS and macOS only.

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

`indicate`

56

ChromeOS and macOS only.

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

`notify`

56

ChromeOS and macOS only.

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

`read`

56

ChromeOS and macOS only.

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

`reliableWrite`

56

ChromeOS and macOS only.

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

`writableAuxiliaries`

56

ChromeOS and macOS only.

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

`write`

56

ChromeOS and macOS only.

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

`writeWithoutResponse`

56

ChromeOS and macOS only.

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BluetoothCharacteristicProperties" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BluetoothCharacteristicProperties</a>
