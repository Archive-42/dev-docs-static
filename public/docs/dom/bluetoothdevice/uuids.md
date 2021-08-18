# BluetoothDevice.uuids

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Use [`BluetoothRemoteGATTServer.getPrimaryServices`](../bluetoothremotegattserver/getprimaryservices) instead.

The `BluetoothDevice.uuids` read-only property lists the UUIDs of GATT services provided by the device, that the current origin is allowed to access.

## Syntax

    var uuids[] = instanceOfBluetoothDevice.uuids

## Returns

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array).

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

`uuids`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BluetoothDevice/uuids" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BluetoothDevice/uuids</a>
