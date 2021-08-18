SerialPort.writable
===================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `writable` read-only property of the [`SerialPort`](../serialport) interface returns a [`WritableStream`](../writablestream) for sending data to the device connected to the port. Chunks written to this stream must be instances of [`BufferSource`](../buffersource) (for example, an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) or [`ArrayBufferView`](../arraybufferview) such as [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array)). This property is non-null as long as the port is open and has not encountered a fatal error.

Syntax
------

    var writableStream = SerialPort.writable;

### Value

A [`WritableStream`](../writablestream)

Examples
--------

The following example shows how to write a string to a port. A [`TextEncoder`](../textencoder) converts the string to a `Uint8Array` before transmission.

    const encoder = new TextEncoder();
    const writer = port.writable.getWriter();
    await writer.write(encoder.encode("PING"));
    writer.releaseLock();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/serial/#dom-serialport-writable">Web Serial API<br />
<span class="small">The definition of 'SerialPort.writable' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`writable`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SerialPort/writable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SerialPort/writable</a>
