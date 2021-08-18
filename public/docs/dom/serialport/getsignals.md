SerialPort.getSignals()
=======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `SerialPort.getSignals()` method of the [`SerialPort`](../serialport) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an object containing the current state of the port's control signals.

Syntax
------

    var promise = SerialPort.getSignals();

### Parameters

None.

### Return value

Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an object containing the following members:

`clearToSend`  
A boolean indicating to the other end of a serial connection that is is clear to send data.

`dataCarrierDetect`  
A boolean that toggles the control signal needed to communicate over a serial connection.

`dataSetReady`  
A boolean indicating whether the device is ready to send and receive data.

`ringIndicator`  
A boolean indicating whether a ring signal should be sent down the serial connection.

### Exceptions

 [`DOMException`](../domexception) `"InvalidStateError"`   
Indicates that the port is not open. Call [`SerialPort.open()`](open) to avoid this error.

 [`DOMException`](../domexception) `NetworkError`   
Indicates that one of the signals on the device could not be set.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/serial/#dom-serialport-getsignals">Web Serial API<br />
<span class="small">The definition of 'SerialPort.getSignals()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getSignals`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SerialPort/getSignals" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SerialPort/getSignals</a>
