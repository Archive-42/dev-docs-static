SerialPort.readable
===================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `readable` read-only property of the [`SerialPort`](../serialport) interface returns a [`ReadableStream`](../readablestream) for receiving data from the device connected to the port. Chunks read from this stream are instances of [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array). This property is non-null as long as the port is open and has not encountered a fatal error.

Syntax
------

    var readableStream = SerialPort.readable;

### Value

A [`ReadableStream`](../readablestream).

Examples
--------

The following example shows how to read data from a port. The outer loop handles non-fatal errors, creating a new reader until a fatal error is encountered and `readable` becomes `null`.

    while (port.readable) {
      const reader = port.readable.getReader();
      try {
        while (true) {
          const { value, done } = await reader.read();
          if (done) {
            // |reader| has been canceled.
            break;
          }
          // Do something with |value|...
        }
      } catch (error) {
        // Handle |error|...
      } finally {
        reader.releaseLock();
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/serial/#dom-serialport-readable">Web Serial API<br />
<span class="small">The definition of 'SerialPort.readable' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`readable`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SerialPort/readable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SerialPort/readable</a>
