RTCDataChannelEvent
===================

Constructor
-----------

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCDataChannelEvent()` constructor returns a new [`RTCDataChannelEvent`](rtcdatachannelevent) object, which represents a <span class="page-not-created">`datachannel`</span> event. These events sent to an [`RTCPeerConnection`](rtcpeerconnection) when its remote peer is asking to open an [`RTCDataChannel`](rtcdatachannel) between the two peers.

You will rarely if ever construct an `RTCDataChannelEvent` by hand; instead, the WebRTC layer will generate and deliver them to you at the appropriate time. Just listen for the [`datachannel`](rtcpeerconnection/datachannel_event) event to be received by the `RTCPeerConnection` and when you receive it, use the [`RTCDataChannelEvent.channel`](rtcdatachannelevent/channel) property to gain access to the data channel which has been opened.

 [`RTCDataChannelEvent()`](rtcdatachannelevent/rtcdatachannelevent) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The `RTCDataChannelEvent()` constructor creates a new `RTCDataChannelEvent`.

 [`channel`](rtcdatachannelevent/channel) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> undefined  
The read-only property `RTCDataChannelEvent``.channel` returns the `RTCDataChannel` associated with the event.

Examples
--------

In this example, the `datachannel` event handler is set up to save the data channel reference and set up handlers for the events which need to be monitored. The [`channel`](rtcdatachannelevent/channel) property provides the [`RTCDataChannel`](rtcdatachannel) representing the connection to the other peer.

    pc.ondatachannel = function(event) {
      inboundDataChannel = event.channel;
      inboundDataChannel.onmessage = handleIncomingMessage;
      inboundDataChannel.onopen = handleChannelOpen;
      inboundDataChannel.onclose = handleChannelClose;
    }

See [A simple RTCDataChannel sample](webrtc_api/simple_rtcdatachannel_sample) for another, more complete, example of how to use data channels.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcdatachannelevent">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannelEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCDataChannelEvent`

Yes

≤79

22

No

Yes

11

Yes

28

22

Yes

11

1.5

`RTCDataChannelEvent`

57

≤79

22

No

44

11

57

57

22

43

11

7.0

`channel`

Yes

≤79

22

No

Yes

11

Yes

28

22

Yes

11

1.5

See also
--------

-   [WebRTC](webrtc_api)
-   [`RTCDataChannel`](rtcdatachannel)
-   <span class="page-not-created">`RTCDataChannel.ondatachannel`</span>
-   [A simple RTCDataChannel sample](webrtc_api/simple_rtcdatachannel_sample)
-   [`RTCPeerConnection`](rtcpeerconnection) (the target interface for `datachannel` events)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannelEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannelEvent</a>
