RTCDataChannel
==============

Properties
----------

The `RTCDataChannel` interface represents a network channel which can be used for bidirectional peer-to-peer transfers of arbitrary data. Every data channel is associated with an [`RTCPeerConnection`](rtcpeerconnection), and each peer connection can have up to a theoretical maximum of 65,534 data channels (the actual limit may vary from browser to browser).

To create a data channel and ask a remote peer to join you, call the [`RTCPeerConnection`](rtcpeerconnection)'s [`createDataChannel()`](rtcpeerconnection/createdatachannel) method. The peer being invited to exchange data receives a `datachannel` event (which has type [`RTCDataChannelEvent`](rtcdatachannelevent)) to let it know the data channel has been added to the connection.

*Also inherits properties from: [`EventTarget`](eventtarget)*

 [`binaryType`](rtcdatachannel/binarytype) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The property `binaryType` on the `RTCDataChannel` interface is a `DOMString` which specifies the type of JavaScript object which should be used to represent binary data received on the `RTCDataChannel`. Values allowed by the `WebSocket.binaryType` property are also permitted here: `"blob"` if `Blob` objects are being used or `"arraybuffer"` if `ArrayBuffer` objects are being used. The default is `"blob"`.

 [`bufferedAmount`](rtcdatachannel/bufferedamount) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> undefined  
The read-only `RTCDataChannel` property `bufferedAmount` returns the number of bytes of data currently queued to be sent over the data channel.

 [`bufferedAmountLowThreshold`](rtcdatachannel/bufferedamountlowthreshold) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The `RTCDataChannel` property `bufferedAmountLowThreshold` is used to specify the number of bytes of buffered outgoing data that is considered "low." The default value is 0.

 [`id`](rtcdatachannel/id) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> undefined  
The read-only `RTCDataChannel` property `id` returns an ID number (between 0 and 65,534) which uniquely identifies the `RTCDataChannel`.

 [`label`](rtcdatachannel/label) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> undefined  
The read-only `RTCDataChannel` property `label` returns a `DOMString` containing a name describing the data channel. These labels are not required to be unique.

 [`maxPacketLifeTime`](rtcdatachannel/maxpacketlifetime) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> undefined  
The read-only `RTCDataChannel` property `maxPacketLifeTime` returns the amount of time, in milliseconds, the browser is allowed to take to attempt to transmit a message, as set when the data channel was created, or `null`.

 [`maxRetransmits`](rtcdatachannel/maxretransmits) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> undefined  
The read-only `RTCDataChannel` property `maxRetransmits` returns the maximum number of times the browser should try to retransmit a message before giving up, as set when the data channel was created, or `null`, which indicates that there is no maximum.

 [`negotiated`](rtcdatachannel/negotiated) undefined  
The read-only `RTCDataChannel` property `negotiated` indicates whether the `RTCDataChannel`'s connection was negotiated by the Web app (`true`) or by the WebRTC layer (`false`).

 [`ordered`](rtcdatachannel/ordered) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> undefined  
The read-only `RTCDataChannel` property `ordered` indicates whether or not the data channel guarantees in-order delivery of messages; the default is `true`, which indicates that the data channel is indeed ordered.

 [`protocol`](rtcdatachannel/protocol) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> undefined  
The read-only `RTCDataChannel` property `protocol` returns a `DOMString` containing the name of the subprotocol in use. If no protocol was specified when the data channel was created, then this property's value is "" (the empty string).

 [`readyState`](rtcdatachannel/readystate) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> undefined  
The read-only `RTCDataChannel` property `readyState` returns an enum of type `RTCDataChannelState` which indicates the state of the data channel's underlying data connection.

 <s>[`reliable`](rtcdatachannel/reliable)</s> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="icon obsolete" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an obsolete API and is no longer guaranteed to work. </span> undefined  
The read-only `RTCDataChannel` property `reliable` indicates whether or not the data channel is reliable.

 <s>[`stream`](rtcdatachannel/stream)</s> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon obsolete" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an obsolete API and is no longer guaranteed to work. </span> undefined  
The deprecated (and never part of the official specification) read-only `RTCDataChannel` property `stream` returns an ID number (between 0 and 65,535) which uniquely identifies the `RTCDataChannel`.

 [`onbufferedamountlow`](rtcdatachannel/onbufferedamountlow) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The `RTCDataChannel.onbufferedamountlow` property is an `EventHandler` which specifies a function the browser calls when the `bufferedamountlow` event is sent to the `RTCDataChannel`. This event, which is represented by a simple `Event` object, is sent when the amount of data buffered to be sent falls to or below the threshold specified by the channel's `RTCDataChannel.bufferedAmountLowThreshold`.

 [`onclose`](rtcdatachannel/onclose) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The `RTCDataChannel.onclose` property is an `EventHandler` which specifies a function to be called by the browser when the `close` event is received by the `RTCDataChannel`. This is a simple `Event` which indicates that the data channel has closed down.

 [`onclosing`](rtcdatachannel/onclosing) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The `RTCDataChannel.onclosing` property is an `EventHandler` which specifies a function to be called by the browser when the `closing` event is received by the `RTCDataChannel`. This is a simple `Event` which indicates that the data channel is being closed, that is, `RTCDataChannel` transitions to "closing" state. For example, after `RTCDataChannel.close` was called but the underlying data transport might not have been closed yet.

 [`onerror`](rtcdatachannel/onerror) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The `RTCDataChannel.onerror` property is an `EventHandler` which specifies a function to be called when the `error` event is received. When an error occurs on the data channel, the function receives as input an `ErrorEvent` object describing the error which occurred.

 [`onmessage`](rtcdatachannel/onmessage) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The `RTCDataChannel.onmessage` property stores an `EventHandler` which specifies a function to be called when the `message` event is fired on the channel. This event is represented by the `MessageEvent` interface. This event is sent to the channel when a message is received from the other peer.

 [`onopen`](rtcdatachannel/onopen) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The `RTCDataChannel.onopen` property is an `EventHandler` which specifies a function to be called when the `open` event is fired; this is a simple `Event` which is sent when the data channel's underlying data transport—the link over which the `RTCDataChannel`'s messages flow—is established or re-established.

[`close()`](rtcdatachannel/close)  
The `RTCDataChannel.close()` method closes the `RTCDataChannel`. Either peer is permitted to call this method to initiate closure of the channel.

[`send()`](rtcdatachannel/send)  
The `send()` method of the `RTCDataChannel` interface sends data across the data channel to the remote peer.

Events
------

[`bufferedamountlow`](rtcdatachannel/bufferedamountlow_event)  
Sent to the channel's [`onbufferedamountlow`](rtcdatachannel/onbufferedamountlow) event handler when the number of bytes of data in the outgoing data buffer falls below the value specified by [`bufferedAmountLowThreshold`](rtcdatachannel/bufferedamountlowthreshold).

[`close`](rtcdatachannel/close_event)  
Sent to the [`onclose`](rtcdatachannel/onclose) event handler when the underlying data transport closes.

[`error`](rtcdatachannel/error_event)  
Sent to the [`onerror`](rtcdatachannel/onerror) event handler when an error occurs on the data channel.

[`message`](rtcdatachannel/message_event)  
Sent to the [`onmessage`](rtcdatachannel/onmessage) event handler when a message has been received from the remote peer. The message contents can be found in the event's [`data`](messageevent/data) property.

[`open`](rtcdatachannel/open_event)  
Sent to the [`onopen`](rtcdatachannel/onopen) event handler when the data channel is first opened, or when an existing data channel's underlying connection re-opens.

Data format
-----------

The underlying data format is defined by the IEEE draft specification `draft-ietf-mmusic-sctp-sdp`. The current format specifies its protocol as either `"UDP/DTLS/SCTP"` (UDP carrying DTLS carrying SCTP) or `"TCP/DTLS/SCTP"` (TCP carrying DTLS carrying SCTP). Older browsers may only specify `"DTLS/SCTP"`.

Example
-------

    var pc = new RTCPeerConnection();
    var dc = pc.createDataChannel("my channel");

    dc.onmessage = function (event) {
      console.log("received: " + event.data);
    };

    dc.onopen = function () {
      console.log("datachannel open");
    };

    dc.onclose = function () {
      console.log("datachannel close");
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcdatachannel">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`RTCDataChannel`

Yes

≤79

24

18-60

No

Yes

11

4.4

29

24

18-60

Yes

11

2.0

`binaryType`

Yes

≤79

18

No

Yes

11

4.4

29

18

Yes

11

2.0

`bufferedAmount`

56

≤79

18

No

43

11

56

56

18

43

11

6.0

`bufferedamountlow_event`

57

The default for `rtcpMuxPolicy is require.`

≤79

The default for `rtcpMuxPolicy is require.`

Yes

No

44

The default for `rtcpMuxPolicy is require.`

Yes

57

The default for `rtcpMuxPolicy is require.`

57

The default for `rtcpMuxPolicy is require.`

Yes

43

The default for `rtcpMuxPolicy is require.`

No

7.0

The default for `rtcpMuxPolicy is require.`

`bufferedAmountLowThreshold`

56

≤79

Yes

No

43

11

56

56

No

43

11

6.0

`close`

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

`close_event`

56

≤79

Yes

No

43

?

56

56

Yes

43

No

6.0

`error_event`

56

≤79

Yes

No

43

?

56

56

Yes

43

No

6.0

`id`

56

≤79

No

No

43

11

56

56

No

43

11

6.0

`label`

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

`maxPacketLifeTime`

56

≤79

62

No

43

11

56

56

62

43

11

6.0

`maxRetransmits`

56

≤79

62

No

43

11

56

56

62

43

11

6.0

`message_event`

56

≤79

Yes

No

43

Yes

56

56

Yes

43

Yes

6.0

`negotiated`

56

≤79

68

No

43

11

56

56

68

43

11

6.0

`onbufferedamountlow`

57

The default for `rtcpMuxPolicy` is `require`.

≤79

The default for `rtcpMuxPolicy` is `require`.

Yes

No

44

The default for `rtcpMuxPolicy` is `require`.

11

57

The default for `rtcpMuxPolicy` is `require`.

57

The default for `rtcpMuxPolicy` is `require`.

Yes

43

The default for `rtcpMuxPolicy` is `require`.

11

7.0

The default for `rtcpMuxPolicy` is `require`.

`onclose`

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

`onclosing`

81

81

No

No

68

No

81

81

No

?

No

13.0

`onerror`

56

≤79

No

No

43

11

56

56

No

43

11

6.0

`onmessage`

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

`onopen`

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

`open_event`

56

≤79

Yes

No

43

Yes

56

56

Yes

43

Yes

6.0

`ordered`

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

`priority`

No

No

?

No

?

No

No

No

?

?

No

No

`protocol`

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

`readyState`

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

`reliable`

56

≤79

No

No

43

No

56

56

No

43

No

6.0

`sctp-sdp-21`

58

≤79

63

No

?

No

58

58

63

?

No

7.0

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

`stream`

56

≤79

No

No

43

No

56

56

No

43

No

6.0

See also
--------

-   [WebRTC API](https://developer.mozilla.org/en-US/docs/Web/Guide/API/WebRTC_API)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel</a>
