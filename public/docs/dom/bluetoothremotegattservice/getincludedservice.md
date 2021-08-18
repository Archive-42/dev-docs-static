# BluetoothRemoteGATTService.getIncludedService()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `BluetoothGATTService.getIncludedService()` method returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to an instance of [`BluetoothRemoteGATTService`](../bluetoothremotegattservice) for a given universally unique identifier (UUID).

## Syntax

    bluetoothGATTServiceInstance.getIncludedService(service).then(function(BluetoothGATTService) { ... } )

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to an instance of [`BluetoothRemoteGATTService`](../bluetoothremotegattservice).

### Properties

service  
The UUID of a Bluetooth service.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webbluetoothcg.github.io/web-bluetooth/#dom-bluetoothremotegattservice-getincludedservice">Web Bluetooth<br />
<span class="small">The definition of 'getIncludedService()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BluetoothRemoteGATTService/getIncludedService" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BluetoothRemoteGATTService/getIncludedService</a>
