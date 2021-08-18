Serial.getPorts()
=================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `getPorts()` method of the [`Serial`](../serial) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an array of [`SerialPort`](../serialport) objects representing serial ports connected to the host which the origin has permission to access.

Syntax
------

    var promise = Serial.getPorts();

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an array of [`SerialPort`](../serialport) objects.

### Exceptions

 [`DOMException`](../domexception) `"SecurityError"`   
The returned `Promise` rejects with this error if a [Feature Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy) restricts use of this API or a permission to use it has not granted via a user gesture.

Examples
--------

The following example uses `getPorts()` to initialize a list of available ports.

    navigator.serial.getPorts().then((ports) => {
      // Initialize the list of available ports with `ports` on page load.
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/serial/#dom-serial-getports">Web Serial API<br />
<span class="small">The definition of 'Serial.getPorts()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Serial/getPorts" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Serial/getPorts</a>
