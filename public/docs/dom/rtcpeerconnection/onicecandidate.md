RTCPeerConnection.onicecandidate
================================

The `RTCPeerConnection` property **[`onicecandidate`](onicecandidate)** property is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) which specifies a function to be called when the `icecandidate` event occurs on an [`RTCPeerConnection`](../rtcpeerconnection) instance. This happens whenever the local [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) agent needs to deliver a message to the other peer through the signaling server. This lets the ICE agent perform negotiation with the remote peer without the browser itself needing to know any specifics about the technology being used for signaling; implement this method to use whatever messaging technology you choose to send the ICE candidate to the remote peer.

Syntax
------

    rtcPeerConnection.onicecandidate = eventHandler;

### Value

This should be set to a function which you provide that accepts as input an [`RTCPeerConnectionIceEvent`](../rtcpeerconnectioniceevent) object representing the `icecandidate` event. The function should deliver the ICE candidate, whose [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) can be found in the event's [`candidate`](../rtcpeerconnectioniceevent/candidate) property, to the remote peer through the signaling server.

If the event's `candidate` property is `null`, ICE gathering has finished. This message should not be sent to the remote peer. When this happens, the connection's [`iceGatheringState`](icegatheringstate) has also changed to `complete`. You don't need to watch for this explicitly; instead, if you need to sense the end of signaling, you should watch for a [`icegatheringstatechange`](icegatheringstatechange_event) event indicating that the ICE negotiation has transitioned to the `complete` state.

Example
-------

The example below, which is based on the code from the article [Signaling and video calling](../webrtc_api/signaling_and_video_calling), sets up a handler for `icecandidate` events to send the candidates to the remote peer.

    pc.onicecandidate = function(event) {
      if (event.candidate) {
        // Send the candidate to the remote peer
      } else {
        // All ICE candidates have been sent
      }
    }

Notice that the end of negotiation is detected here when the event's [`candidate`](../rtcpeerconnectioniceevent/candidate) property is `null`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-onicecandidate">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.onicecandidate' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onicecandidate`

24

15

22

No

43

Promise-based version.

37-43

11

≤37

Yes

44

43

Promise-based version.

37-43

11

6.0

See also
--------

-   The `icecandidate` event and its type, [`RTCPeerConnectionIceEvent`](../rtcpeerconnectioniceevent).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onicecandidate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onicecandidate</a>
