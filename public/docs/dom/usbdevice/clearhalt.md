USBDevice.clearHalt()
=====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `clearHalt()` method of the [`USBDevice`](../usbdevice) interface returns a [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when a halt condition is cleared. A halt condition is when a data tranfer to or from the device has a status of `'stall'`, which requires the web page (the *host* system, in USB terminology) to clear that condition. See the for details.

Syntax
------

    var promise = USBDevice.clearHalt(direction, endpointNumber)

### Parameters

direction  
Indicates whether the devices input or output should be cleared. Valid values are `'in'` or `'out'`.

endpointNumber  
Indicates the number of the endpoint to clear. The promise will reject if an invalid endpoint is supplied.

### Return value

A [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

Example
-------

The following example shows how to test for and clear a `'stall'` condition in the result of a data transfer.

What data can be passed to a USB device and how it is passed is particular and unique to each device.

    while (true) {
      let result = await data.transferIn(1, 6);

      if (result.data && result.data.byteLength === 6) {
        console.log('Channel 1: ' + result.data.getUint16(0));
        console.log('Channel 2: ' + result.data.getUint16(2));
        console.log('Channel 5: ' + result.data.getUint16(4));
      }

      if (result.status === 'stall') {
        console.warn('Endpoint stalled. Clearing.');
        await device.clearHalt('in', 1);
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#dom-usbdevice-clearhalt">WebUSB<br />
<span class="small">The definition of 'clearHalt()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`clearHalt`

61

79

No

No

48

No

No

61

No

45

No

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/clearHalt" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBDevice/clearHalt</a>
