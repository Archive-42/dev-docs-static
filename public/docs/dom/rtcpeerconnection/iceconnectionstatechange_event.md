RTCPeerConnection: iceconnectionstatechange event
=================================================

An `iceconnectionstatechange` event is sent to an [`RTCPeerConnection`](../rtcpeerconnection) object each time the [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) connection state changes during the negotiation process. The new ICE connection state is available in the object's [`iceConnectionState`](iceconnectionstate) property.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="oniceconnectionstatechange"><code>oniceconnectionstatechange</code></a></td></tr></tbody></table>

One common task performed by the `iceconnectionstatechange` event listener: to trigger ICE restart when the state changes to `failed`. See [ICE restart](../webrtc_api/session_lifetime#ice_restart) in [Lifetime of a WebRTC session](../webrtc_api/session_lifetime) for further information.

Usage notes
-----------

A successful connection attempt will typically involve the state starting at `new`, then transitioning through `checking`, then `connected`, and finally `completed`. However, under certain circumstances, the `connected` state can be skipped, causing a connection to transition directly from the `checking` state to `completed`. This can happen when only the last checked candidate is successful, and the gathering and end-of-candidates signals both occur before the successful negotiation is completed.

### ICE connection state during ICE restarts

When an ICE restart is processed, the gathering and connectivity checking process is started over from the beginning, which will cause the `iceConnectionState` to transition to `connected` if the ICE restart was triggered while in the `completed` state. If ICE restart is initiated while in the transient `disconnected` state, the state transitions instead to `checking`, essentially indicating that the negotiation is ignoring the fact that the connection had been temporarily lost.

### State transitions as negotiation ends

When the negotiation process runs out of candidates to check, the ICE connection transitions to one of two states. If no suitable candidates were found, the state transitions to `failed`. If at least one suitable candidate was successfully identified, the state transitions to `completed`. The ICE layer makes this determination upon receiving the end-of-candidates signal, which is provided by caling [`addIceCandidate()`](addicecandidate) with a candidate whose [`candidate`](../rtcicecandidate/candidate) property is an empty string (""), or by setting the [`RTCPeerConnection`](../rtcpeerconnection) property [`canTrickleIceCandidates`](cantrickleicecandidates) to `false`.

Examples
--------

An event handler for this event can be added using the [`RTCPeerConnection.oniceconnectionstatechange`](oniceconnectionstatechange) property or by using [`addEventListener()`](../eventtarget/addeventlistener) on the `RTCPeerConnection`.

In this example, a handler for `iceconnectionstatechange` is set up to update a call state indicator by using the value of [`iceConnectionState`](iceconnectionstate) to create a string which corresponds to the name of a CSS class that we can assign to the status indicator to cause it to reflect the current state of the connection.

    pc.addEventListener("iceconnectionstatechange", ev => {
      let stateElem = document.querySelector("#call-state");
      stateElem.className = `${pc.iceConnectionState}-state`;
    }, false);

This can also be written as:

    pc.oniceconnectionstatechange = ev => {
      let stateElem = document.querySelector("#call-state");
      stateElem.className = `${pc.iceConnectionState}-state`;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-iceconnectionstatechange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'iceconnectionstatechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`iceconnectionstatechange_event`

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

?

6.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [`RTCPeerConnection`](../rtcpeerconnection)
-   [`RTCPeerConnection.onIceConnectionStateChange`](oniceconnectionstatechange)
-   [`RTCPeerConnection.iceConnectionState`](iceconnectionstate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceconnectionstatechange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceconnectionstatechange_event</a>
