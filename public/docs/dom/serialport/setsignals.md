SerialPort.setSignals()
=======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `setSignals()` method of the [`SerialPort`](../serialport) interface sets control signals on the port and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when they are set.

Syntax
------

    var promise = SerialPort.setSignals(options);

### Parameters

 `options`<span class="badge inline optional">Optional</span>   
An object with any of the following values:

`clearToSend`  
A boolean indicating to the other end of a serial connection that is is clear to send data.

`dataCarrierDetect`  
A boolean that toggles the control signal needed to communicate over a serial connection.

`dataSetReady`  
A boolean indicating whether the device is ready to send and receive data.

`ringIndicator`  
A boolean indicating whether a ring signal should be sent down the serial connection.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

### Exceptions

 [`DOMException`](../domexception) `"InvalidStateError"`   
Indicates that the port is not open. Call [`SerialPort.open()`](open) to avoid this error.

 [`DOMException`](../domexception) `NetworkError`   
Indicates that one of the signals on the device could not be set.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/serial/#dom-serialport-setsignals">Web Serial API<br />
<span class="small">The definition of 'SerialPort.setSignals()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`setSignals`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SerialPort/setSignals" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SerialPort/setSignals</a>
