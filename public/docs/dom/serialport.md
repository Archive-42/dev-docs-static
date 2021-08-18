SerialPort
==========

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

Description
-----------

The `SerialPort` interface of the <span class="page-not-created">`Web Serial API`</span> provides access to a serial port on the host device.

Constructor
-----------

Instances of this interface may be obtained by calling methods of the [`Serial`](serial) interface, therefore it has no constructor of its own.

Properties
----------

 [`SerialPort.readable`](serialport/readable)<span class="badge inline readonly">Read only </span>   
Returns a [`ReadableStream`](readablestream) for receiving data from the device connected to the port.

 [`SerialPort.writable`](serialport/writable)<span class="badge inline readonly">Read only </span>   
Returns a [`WritableStream`](writablestream) for sending data to the device connected to the port.

### Event handlers

[`SerialPort.onconnect`](serialport/onconnect)  
An event handler called when the port has connected to the device.

[`SerialPort.ondisconnect`](serialport/ondisconnect)  
An event handler called when the port has disconnected from the device.

Methods
-------

[`SerialPort.getInfo()`](serialport/getinfo)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an object containing properties of the port.

[`SerialPort.open()`](serialport/open)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the port is opened. By default the port is opened with 8 data bits, 1 stop bit and no parity checking.

[`SerialPort.setSignals()`](serialport/setsignals)  
Sets control signals on the port and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when they are set.

[`SerialPort.getSignals()`](serialport/getsignals)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an object containing the current state of the port's control signals.

[`SerialPort.close()`](serialport/close)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the port closes.

Examples
--------

### Opening a port

Before communicating on a serial port it must be opened. Opening the port allows the site to specify the necessary parameters that control how data is transmitted and received. Developers should check the documentation for the device they are connecting to for the appropriate parameters.

    await port.open({ baudRate: /* pick your baud rate */ });

Once the `Promise` returned by `open()` resolves the `readable` and `writable` attributes can be accessed to get the [`ReadableStream`](readablestream) and [`WritableStream`](writablestream) instances for receiving data from and sending data to the connected device.

### Reading data from a port

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

### Writing data to a port

The following example shows how to write a string to a port. A [`TextEncoder`](textencoder) converts the string to a `Uint8Array` before transmission.

    const encoder = new TextEncoder();
    const writer = port.writable.getWriter();
    await writer.write(encoder.encode("PING"));
    writer.releaseLock();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/serial/#dom-serialport">Web Serial API<br />
<span class="small">The definition of 'SerialPort' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`SerialPort`

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

`close`

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

`getInfo`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SerialPort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SerialPort</a>
