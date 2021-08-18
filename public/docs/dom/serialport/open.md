SerialPort.open()
=================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `open()` method of the [`SerialPort`](../serialport) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the port is opened. By default the port is opened with 8 data bits, 1 stop bit and no parity checking. The `baudRate` parameter is required.

Syntax
------

    var promise = SerialPort.open(options);

### Parameters

*`options`*  
An object with any of the following values:

`baudRate`  
A positive, non-zero value indicating the baud rate at which serial communication should be established.

 `bufferSize`<span class="badge inline optional">Optional</span>   
An unsigned long integer indicating the size of the read and write buffers that are to be established. If not passed, defaults to 255.

 `dataBits`<span class="badge inline optional">Optional</span>   
An integer value of 7 or 8 indicating the number of data bits per frame. If not passed, defaults to 8.

 `flowControl`<span class="badge inline optional">Optional</span>   
The flow control type, either `"none"` or `"hardware"`. The default value is `"none:`.

 `parity`<span class="badge inline optional">Optional</span>   
The parity mode, either `"none"`, `"even"`, or `"odd"`. The default value is `"none"`.

 `stopBits`<span class="badge inline optional">Optional</span>   
An integer value of 1 or 2 indicating the number of stop bits at the end of the frame. If not passed, defaults to 1.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

### Exceptions

 [`DOMException`](../domexception) `"InvalidStateError"`   
Indicates that the port is already open.

 [`DOMException`](../domexception) `NetworkError`   
Indicates that the attempt to open the port failed.

Examples
--------

Before communicating on a serial port it must be opened. Opening the port allows the site to specify the necessary parameters that control how data is transmitted and received. Developers should check the documentation for the device they are connecting to for the appropriate parameters.

    await port.open({ baudRate: /* pick your baud rate */ });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/serial/#dom-serialport-open">Web Serial API<br />
<span class="small">The definition of 'SerialPort.open()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`open`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SerialPort/open" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SerialPort/open</a>
