RTCPeerConnection: signalingstatechange event
=============================================

An `signalingstatechange` event is sent to an [`RTCPeerConnection`](../rtcpeerconnection) to notify it that its signaling state, as indicated by the [`signalingState`](signalingstate) property, has changed.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onsignalingstatechange"><code>RTCPeerConnection.onsignalingstatechange</code></a></td></tr></tbody></table>

Examples
--------

Given an [`RTCPeerConnection`](../rtcpeerconnection), `pc`, and an `updateStatus()` function that presents status information to the user, this code sets up an event handler to let the user know when the ICE negotiation process finishes up.

    pc.addEventListener("signalingstatechange", ev => {
      switch(pc.signalingState) {
        case "stable":
          updateStatus("ICE negotiation complete");
          break;
      }
    }, false);

Using [`onsignalingstatechange`](onsignalingstatechange), it looks like this:

    pc.onsignalingstatechange = ev => {
      switch(pc.signalingState) {
        case "stable":
          updateStatus("ICE negotiation complete");
          break;
        }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-signalingstatechange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'signalingstatechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`signalingstatechange_event`

28

15

22

No

43

11

Yes

28

44

43

No

6.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [`RTCPeerConnection.signalingState`](signalingstate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/signalingstatechange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/signalingstatechange_event</a>
