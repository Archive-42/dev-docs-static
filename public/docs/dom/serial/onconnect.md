Serial.onconnect
================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `onconnect` [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) of the [`Serial`](../serial) interface is called when a port has been connected from a device. This method receives an [`Event`](../event) object. The target of this event is the [`SerialPort`](../serialport) interface that has been disconnected.

This event is only fired for ports associated with removable devices such as those connected via USB. The user must grant the origin permission to access this device during a call to [`requestPort()`](requestport) before this event will be fired.

Syntax
------

    Serial.onconnect = function(event);
    Serial.addEventListener('connect', function(event));

Example
-------

The following example shows an event listener for the `connect` event,. This allows the site to react when a port is connected.

    navigator.serial.addEventListener('connect', (e) => {
      // Connect to `e.target` or add it to a list of available ports.
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/serial/#dom-serial-onconnect">Web Serial API<br />
<span class="small">The definition of 'Serial.onconnect' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Serial/onconnect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Serial/onconnect</a>
