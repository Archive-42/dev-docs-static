WebSocket.send()
================

The `WebSocket.send()` method enqueues the specified data to be transmitted to the server over the WebSocket connection, increasing the value of `bufferedAmount` by the number of bytes needed to contain the data. If the data can't be sent (for example, because it needs to be buffered but the buffer is full), the socket is closed automatically.

Syntax
------

    WebSocket.send("Hello server!");

### Parameters

`data`  
The data to send to the server. It may be one of the following types:

[`USVString`](../usvstring)  
A text string. The string is added to the buffer in UTF-8 format, and the value of `bufferedAmount` is increased by the number of bytes required to represent the UTF-8 string.

[`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer)  
You can send the underlying binary data used by a typed array object; its binary data contents are queued in the buffer, increasing the value of `bufferedAmount` by the requisite number of bytes.

[`Blob`](../blob)  
Specifying a `Blob` enqueues the blob's raw data to be transmitted in a binary frame. The value of `bufferedAmount` is increased by the byte size of that raw data.

[`ArrayBufferView`](../arraybufferview)  
You can send any [JavaScript typed array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays) object as a binary frame; its binary data contents are queued in the buffer, increasing the value of `bufferedAmount` by the requisite number of bytes.

### Exceptions thrown

`INVALID_STATE_ERR`  
The connection is not currently `OPEN`.

`SYNTAX_ERR`  
The data is a string that has unpaired surrogates.

**Note:** Gecko's implementation of the `send()` method differs somewhat from the specification in Gecko 6.0; Gecko returns a `boolean` indicating whether or not the connection is still open (and, by extension, that the data was successfully queued or transmitted); this is corrected in Gecko 8.0.

As of Gecko 11.0, support for [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) is implemented but not [`Blob`](../blob) data types.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-websocket-send">HTML Living Standard<br />
<span class="small">The definition of 'WebSocket: send' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`send`

4

12

18

See [bug 775368](https://bugzil.la/775368).

11-18

Only parameter of type `ArrayBuffer` and `String` supported.

8-11

Only parameter of type `String` supported.

4-8

Only parameter of type `String` supported. Returns `boolean`.

10

12.1

5

≤37

18

18

See [bug 775368](https://bugzil.la/775368).

14-18

Only parameter of type `ArrayBuffer` and `String` supported.

8-14

Only parameter of type `String` supported.

4-8

Only parameter of type `String` supported. Returns `boolean`.

12.1

4.2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/send" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/send</a>
