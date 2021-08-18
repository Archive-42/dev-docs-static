SerialPort.onconnect
====================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `onconnect` event handler of the [`SerialPort`](../serialport) interface is called when the port has disconnected from the device. This method receives an [`Event`](../event) object. This event is only fired for ports associated with removable devices such as those connected via USB. This event bubbles to the instance of [`Serial`](../serial) that returned this interface..

Syntax
------

    SerialPort.onconnect = function(event);
    SerialPort.addEventListener('connect', function(event));

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/serial/#dom-serialport-onconnect">Web Serial API<br />
<span class="small">The definition of 'SerialPort.onconnect' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SerialPort/onconnect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SerialPort/onconnect</a>
