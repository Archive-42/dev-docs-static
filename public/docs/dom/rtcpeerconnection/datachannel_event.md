RTCPeerConnection: datachannel event
====================================

A `datachannel` event is sent to an [`RTCPeerConnection`](../rtcpeerconnection) instance when an [`RTCDataChannel`](../rtcdatachannel) has been added to the connection, as a result of the remote peer calling [`RTCPeerConnection.createDataChannel()`](createdatachannel).

**Note:** This event is *not* dispatched when the local end of the connection creates the channel.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../rtcdatachannelevent"><code>RTCDataChannelEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="ondatachannel"><code>ondatachannel</code></a></td></tr></tbody></table>

Examples
--------

This example sets up a function that handles `datachannel` events by gathering the information needed to communicate with the newly added [`RTCDataChannel`](../rtcdatachannel) and by adding event handlers for the events that occur on that channel.

    pc.addEventListener("datachannel", ev => {
      receiveChannel = ev.channel;
      receiveChannel.onmessage = myHandleMessage;
      receiveChannel.onopen = myHandleOpen;
      receiveChannel.onclose = myHandleClose;
    }, false);

`receiveChannel` is set to the value of the event's [`channel`](../rtcdatachannelevent/channel) property, which specifies the `RTCDataChannel` object representing the data channel linking the remote peer to the local one.

This same code can also instead use the [`RTCPeerConnection`](../rtcpeerconnection) interface's [`ondatachannel`](ondatachannel) event handler property, like this:

    pc.ondatachannel = ev => {
      receiveChannel = ev.channel;
      receiveChannel.onmessage = myHandleMessage;
      receiveChannel.onopen = myHandleOpen;
      receiveChannel.onclose = myHandleClose;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-datachannel">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'datachannel' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Basic definition.</td></tr></tbody></table>

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

`datachannel_event`

25

≤18

22

No

43

11

Yes

25

44

43

?

6.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [Using WebRTC data channels](../webrtc_api/using_data_channels)
-   [A simple RTCDataChannel sample](../webrtc_api/simple_rtcdatachannel_sample)
-   [`RTCDataChannelEvent`](../rtcdatachannelevent)
-   [`RTCPeerConnection.ondatachannel`](ondatachannel)
-   [`RTCPeerConnection.createDataChannel()`](createdatachannel)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/datachannel_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/datachannel_event</a>
