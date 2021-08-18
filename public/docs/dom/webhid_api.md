WebHID API
==========

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

A Human Interface Device (HID) is a type of device that takes input from or provides output to humans. It also refers to the HID protocol, a standard for bi-directional communication between a host and a device that is designed to simplify the installation procedure. The HID protocol was originally developed for USB devices but has since been implemented over many other protocols, including Bluetooth.

Interfaces
----------

[`HID`](hid)  
Provides methods for connecting to HID devices, listing attached HID devices and event handlers for connected HID devices.

<!-- -->

<span class="page-not-created">`HIDDevice`</span>  
Represents an HID device. It's possible for a single physical device to be represented by multiple \`HIDDevice\` obects.

<!-- -->

<span class="page-not-created">`HIDInputReportEvent`</span>  
Passed to <span class="page-not-created">`HIDDevice.oninputreport`</span> when an input report is received from any associated HID device.

<!-- -->

<span class="page-not-created">`HIDConnectionEvent`</span>  
Passed to <span class="page-not-created">`HID.onconnect`</span> and <span class="page-not-created">`HID.ondisconnect`</span> when a device is connected or disconnected.

Examples
--------

You can connect to a device with <span class="page-not-created">`HID.requestDevices`</span>. In this case, we select from all the available devices.

    const device = await navigator.hid.requestDevice({filters: []})
    // A popup titled `... wants to connect to a HID Device` with `Cancel` and `Connect` buttons will show up with a device list to select from.
    // Select one and click on `Connect` button. Then the device will be an array with the selected device in it.

We can retrieve all the connected devices and log the device names to the console.

    let devices = await navigator.hid.getDevices();
    devices.forEach(device => {
        console.log(`HID: ${device.productName}`);
    });

We can register event listeners for disconnection of any HID devices.

    navigator.hid.addEventListener('disconnect', (event) => {
        console.log(`HID disconnected: ${event.device.productName}`);
        console.dir(event)
    });
    // For example, when my connected keyboard gets disconnected, the log in the console will show:
    // HID disconnected: USB USB Keyboard
    // {
    //    bubbles: false
    //    cancelBubble: false
    //    cancelable: false
    //    composed: false
    //    currentTarget: HID {onconnect: null, ondisconnect: null}
    //    defaultPrevented: false
    //    device: HIDDevice {oninputreport: null, opened: false, vendorId: 6700, productId: 11555, productName: "USB USB Keyboard", …}
    //    eventPhase: 0
    //    isTrusted: true
    //    path: []
    //    returnValue: true
    //    srcElement: HID {onconnect: null, ondisconnect: null}
    //    target: HID {onconnect: null, ondisconnect: null}
    //    timeStamp: 18176.600000023842
    //    type: "disconnect"
    // }

    // The event above is an instance of the HIDConnectionEvent interface.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webhid/">WebHID API</a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WebHID_API`

89

89

No

No

75

No

No

No

No

No

No

No

`getDevices`

89

89

No

No

75

No

No

No

No

No

No

No

`onconnect`

89

89

No

No

75

No

No

No

No

No

No

No

`ondisconnect`

89

89

No

No

75

No

No

No

No

No

No

No

`requestDevice`

89

89

No

No

75

No

No

No

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebHID_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebHID_API</a>
