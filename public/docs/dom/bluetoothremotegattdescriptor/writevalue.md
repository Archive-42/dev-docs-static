# BluetoothRemoteGATTDescriptor.writeValue()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `BluetoothRemoteGATTDescriptor.writeValue()` method sets the value property to the bytes contained in an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Syntax

    BluetoothRemoteGATTDescriptor.writeValue(array[]).then(function() { ... })

### Parameters

array  
Sets the value with the bytes contained in the array.

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webbluetoothcg.github.io/web-bluetooth/#dom-bluetoothremotegattdescriptor-writevalue">Web Bluetooth<br />
<span class="small">The definition of 'writeValue()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BluetoothRemoteGATTDescriptor/writeValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BluetoothRemoteGATTDescriptor/writeValue</a>
