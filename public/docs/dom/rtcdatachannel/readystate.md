RTCDataChannel.readyState
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `RTCDataChannel` property `readyState` returns an enum of type `RTCDataChannelState` which indicates the state of the data channel's underlying data connection.

Syntax
------

    var state = aDataChannel.readyState;

### Values

A string which is one of the values in the [RTCDataChannelState](#rtcdatachannelstate_enum) enum, indicating the current state of the underlying data transport.

#### RTCDataChannelState enum

The `RTCDataChannelState` enum defines string constants which reflect the current status of the [`RTCDataChannel`](../rtcdatachannel)'s underlying data connection.

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>"connecting"</code></td><td>The user agent (browser) is in the process of creating the underlying data transport; that is, whatever network level connection is used to link the two peers together is in the process of being set up. This is the state of a new <a href="../rtcdatachannel"><code>RTCDataChannel</code></a> after being created by <a href="../rtcpeerconnection/createdatachannel"><code>RTCPeerConnection.createDataChannel()</code></a> (on the peer which started the connection process).</td></tr><tr class="even"><td><code>"open"</code></td><td>The underlying data transport has been established and data can be transferred bidirectionally across it. This is the default state of a new <a href="../rtcdatachannel"><code>RTCDataChannel</code></a> created by the WebRTC layer when the remote peer created the channel and delivered to the site or app in a <code>datachannel</code> event of type <a href="../rtcdatachannelevent"><code>RTCDataChannelEvent</code></a>.</td></tr><tr class="odd"><td><code>"closing"</code></td><td>The process of closing the underlying data transport has begun. It is no longer possible to queue new messages to be sent, but previously queued messages may still be send or received before entering the <code>"closed"</code> state.</td></tr><tr class="even"><td><code>"closed"</code></td><td>The underlying data transport has closed, or the attempt to make the connection failed.</td></tr></tbody></table>

Example
-------

    var dataChannel = peerConnection.createDataChannel("File Transfer");
    var sendQueue = [];

    function sendMessage(msg) {
      switch(dataChannel.readyState) {
        case "connecting":
          console.log("Connection not open; queueing: " + msg);
          sendQueue.push(msg);
          break;
        case "open":
          sendQueue.forEach((msg) => dataChannel.send(msg));
          break;
        case "closing":
          console.log("Attempted to send message while closing: " + msg);
          break;
        case "closed":
          console.log("Error! Attempt to send while connection closed.");
          break;
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-datachannel-readystate">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.readyState' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

See also
--------

-   [WebRTC](../webrtc_api)
-   [Using WebRTC data channels](../webrtc_api/using_data_channels)
-   [`RTCDataChannel`](../rtcdatachannel)
-   [`RTCPeerConnection.createDataChannel()`](../rtcpeerconnection/createdatachannel)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/readyState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/readyState</a>
