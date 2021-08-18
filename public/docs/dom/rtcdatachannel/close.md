# RTCDataChannel.close()

The `RTCDataChannel.close()` method closes the [`RTCDataChannel`](../rtcdatachannel). Either peer is permitted to call this method to initiate closure of the channel.

Closure of the data channel is not instantaneous. Most of the process of closing the connection is handled asynchronously; you can detect when the channel has finished closing by watching for a `close` event on the data channel.

The sequence of events which occurs in response to this method being called:

1.  [`RTCDataChannel.readyState`](readystate) is set to `"closing"`.
2.  A background task is established to handle the remainder of the steps below, and `close()` returns to the caller.
3.  The transport layer deals with any buffered messages; the protocol layer decides whether to send them or discard them.
4.  The underlying data transport is closed.
5.  The [`RTCDataChannel.readyState`](readystate) property is set to `"closed"`.
6.  If the transport was closed with an error, the `RTCDataChannel` is sent a `NetworkError` event.
7.  A <span class="page-not-created">`close`</span> event is sent to the channel.

In Firefox, the [`RTCDataChannel`](../rtcdatachannel) interface was implemented under the name `DataChannel` until Firefox 24, so this method was called `DataChannel.close()`.

## Syntax

    RTCDataChannel.close();

## Parameters

None.

## Return value

`undefined`.

## Example

    var pc = new RTCPeerConnection();
    var dc = pc.createDataChannel("my channel");

    dc.onmessage = function (event) {
      console.log("received: " + event.data);
      dc.close(); // We decided to close after the first received message
    };

    dc.onopen = function () {
      console.log("datachannel open");
    };

    dc.onclose = function (
      console.log("datachannel close");
    };

    // Now negotiate the connection and so forth...

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdatachannel-close">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.close()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

## Browser compatibility

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

## See also

- [WebRTC](../webrtc_api)
- [`RTCDataChannel`](../rtcdatachannel)
- [`RTCDataChannel.readyState`](readystate)
- `close` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/close" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/close</a>
