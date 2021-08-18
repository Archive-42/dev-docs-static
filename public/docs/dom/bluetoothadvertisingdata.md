# BluetoothAdvertisingData

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The BluetoothDevice interface of the [Web Bluetooth API](web_bluetooth_api) provides advertising data about a particular Bluetooth device.

## Interface

    interface BluetoothAdvertisingData {
      readonly attribute unsigned short? appearance;
      readonly attribute byte? txPower;
      readonly attribute byte? rssi;
      readonly attribute Map manufacturerData;
      readonly attribute Map serviceData;
    };

## Properties

[`BluetoothAdvertisingData.appearance`](bluetoothadvertisingdata/appearance) <span class="badge inline readonly">Read only </span>  
Returns one of the values defined by the `org.bluetooth.characteristic.gap.appearance` characteristic.

[`BluetoothAdvertisingData.txPower`](bluetoothadvertisingdata/txpower) <span class="badge inline readonly">Read only </span>  
Returns the transmission power at which the device is broadcasting, measured in dBm. This is used to compute the path loss as `this.txPower - this.rssi`.

[`BluetoothAdvertisingData.rssi`](bluetoothadvertisingdata/rssi) <span class="badge inline readonly">Read only </span>  
Returns the power at which the device’s packets are being received, measured in dBm. This is used to compute the path loss as `this.txPower - this.rssi`.

[`BluetoothAdvertisingData.manufacturerData`](bluetoothadvertisingdata/manufacturerdata) <span class="badge inline readonly">Read only </span>  
Returns a map that relates Company Identifier Codes to [`ArrayBuffers`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer).

[`BluetoothAdvertisingData.serviceData`](bluetoothadvertisingdata/servicedata) <span class="badge inline readonly">Read only </span>  
Returns a map that relates UUIDs to [`ArrayBuffers`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer).

## Methods

None.

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

`BluetoothAdvertisingData`

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

`appearance`

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

`manufacturerData`

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

`serviceData`

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

`txPower`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BluetoothAdvertisingData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BluetoothAdvertisingData</a>
