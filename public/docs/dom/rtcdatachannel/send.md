RTCDataChannel.send()
=====================

The `send()` method of the [`RTCDataChannel`](../rtcdatachannel) interface sends data across the data channel to the remote peer. This can be done any time except during the initial process of creating the underlying transport channel. Data sent before connecting is buffered if possible (or an error occurs if it's not possible), and is also buffered if sent while the connection is closing or closed.

Different browsers have different limitations on the size of the message you can send. Specifications exist to define how to automatically fragment large messages, but not all browsers implement them, and those that do have various additional restrictions. This will get less complicated over time, but for now, if you have questions, see [Understanding message size limits](../webrtc_api/using_data_channels#understanding_message_size_limits) in [Using WebRTC data channels](../webrtc_api/using_data_channels).

Syntax
------

    RTCDataChannel.send(data);

### Parameters

`data`  
The data to transmit across the connection. This may be a [`USVString`](../usvstring), a [`Blob`](../blob), an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), or an [`ArrayBufferView`](../arraybufferview).

### Return value

`undefined`.

### Exceptions

`InvalidStateError`  
Since the data channel uses a separate transport channel from the media content, it must establish its own connection; if it hasn't finished doing so (that is, its [`readyState`](readystate) is `"connecting")`, this error occurs without sending or buffering the `data`.

`NetworkError`  
The specified `data` would need to be buffered, and there isn't room for it in the buffer. In this scenario, the underlying transport is immediately closed.

`TypeError`  
The specified `data` is too large for the other peer to receive. Since there are multiple techniques for breaking up large data into smaller pieces for transfer, it's possible to encounter scenarios in which the other peer does not support the same ones. For example, if one peer is a modern browser that supports using the `EOR` (End of Record) flag to indicate when a received message is the last piece of a multi-part object sent using `send()`. For more information about message size restrictions, see [Understanding message size limits](#) in [Using WebRTC data channels](../webrtc_api/using_data_channels).

Example
-------

In this example, a routine called `sendMessage()` is created; it accepts an object as input and sends to the remote peer, over the [`RTCDataChannel`](../rtcdatachannel), a JSON string with the specified object and a time stamp.

    var pc = new RTCPeerConnection();
    var dc = pc.createDataChannel("BackChannel");

    function sendMessage(msg) {
      let obj = {
        "message": msg,
        "timestamp": new Date()
      }
      dc.send(JSON.stringify(obj));
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdatachannel-send">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.send()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

56

≤79

Yes

No

43

11

56

56

Yes

43

11

6.0

See also
--------

-   [WebRTC](../webrtc_api)
-   [`RTCDataChannel`](../rtcdatachannel)
-   [`RTCDataChannel.readyState`](readystate)
-   `close` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/send" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/send</a>
