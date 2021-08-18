# BluetoothAdvertisingData.rssi

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `rssi` read-only property of the [`BluetoothAdvertisingData`](../bluetoothadvertisingdata) interface returns the power at which the device’s packets are being received, measured in dBm. This is used to compute the path loss as `this.txPower - this.rssi`.

## Syntax

    var rssi = BluetoothAdvertisingData.rssi;

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

`rssi`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BluetoothAdvertisingData/rssi" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BluetoothAdvertisingData/rssi</a>
