Serial
======

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

Description
-----------

The `Serial` interface of the <span class="page-not-created">`Web Serial API`</span> provides attributes and methods for finding and connecting to serial ports from a web page.

Event Handlers
--------------

[`Serial.onconnect`](serial/onconnect)  
An event handler called when a port has been connected to the device.

[`Serial.ondisconnect`](serial/ondisconnect)  
An event handler called when a port has been disconnected from the device.

Methods
-------

[`Serial.requestPort()`](serial/requestport)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an instance of [`SerialPort`](serialport) representing the device chosen by the user or rejects if no device was selected.

This method must be called with user activation.

[`Serial.getPorts()`](serial/getports)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an array of [`SerialPort`](serialport) objects representing serial ports connected to the host which the origin has permission to access.

Examples
--------

The following example shows how a site can check for available ports and allow the user to grant it permission to access additional ports.

On load event listeners are added for the `connect` and `disconnect` events so that the site can react when a device is connected or disconnected from the system. The [`getPorts()`](serial/getports) method is then called to see which ports are connected that the site already has access to.

If the site doesn't have access to any connected ports it has to wait until it has user activation to proceed. In this example we use a [`click`](element/click_event) event handler on a button for this task. A filter is passed to [`requestPort()`](serial/requestport) with a USB vendor ID in order to limit the set of devices shown to the user to only USB devices built by a particular manufacturer.

    navigator.serial.addEventListener('connect', (e) => {
      // Connect to `e.target` or add it to a list of available ports.
    });

    navigator.serial.addEventListener('disconnect', (e) => {
      // Remove `e.target` from the list of available ports.
    });

    navigator.serial.getPorts().then((ports) => {
      // Initialize the list of available ports with `ports` on page load.
    });

    button.addEventListener('click', () => {
      const usbVendorId = ...;
      navigator.serial.requestPort({ filters: [{ usbVendorId }]}).then((port) => {
        // Connect to `port` or add it to the list of available ports.
      }).catch((e) => {
        // The user didn't select a port.
      });
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/serial/#serial-interface">Web Serial API<br />
<span class="small">The definition of 'Serial' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Serial`

89

89

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

`getPorts`

89

89

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

`onconnect`

89

89

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

`ondisconnect`

89

89

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

`requestPort`

89

89

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Serial" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Serial</a>
