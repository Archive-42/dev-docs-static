RTCPeerConnection.iceConnectionState
====================================

The read-only property `RTCPeerConnection.iceConnectionState` returns an enum of type `RTCIceConnectionState` which state of the ICE agent associated with the [`RTCPeerConnection`](../rtcpeerconnection).

You can detect when this value has changed by watching for the `iceconnectionstatechange` event.

Syntax
------

     var state = RTCPeerConnection.iceConnectionState;

### Value

The current state of the ICE agent and its connection. The value is one of the strings in the [`RTCIceConnectionState` enum](#rtciceconnectionstate_enum).

### RTCIceConnectionState enum

The `RTCIceConnectionState` enum defines the string constants used to describe the current state of the ICE agent and its connection to the ICE server (that is, the [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) or [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server).

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>"new"</code></td><td>The ICE agent is gathering addresses or is waiting to be given remote candidates through calls to <a href="addicecandidate"><code>RTCPeerConnection.addIceCandidate()</code></a> (or both).</td></tr><tr class="even"><td><code>"checking"</code></td><td>The ICE agent has been given one or more remote candidates and is checking pairs of local and remote candidates against one another to try to find a compatible match, but has not yet found a pair which will allow the peer connection to be made. It's possible that gathering of candidates is also still underway.</td></tr><tr class="odd"><td><code>"connected"</code></td><td>A usable pairing of local and remote candidates has been found for all components of the connection, and the connection has been established. It's possible that gathering is still underway, and it's also possible that the ICE agent is still checking candidates against one another looking for a better connection to use.</td></tr><tr class="even"><td><code>"completed"</code></td><td>The ICE agent has finished gathering candidates, has checked all pairs against one another, and has found a connection for all components.</td></tr><tr class="odd"><td><code>"failed"</code></td><td>The ICE candidate has checked all candidates pairs against one another and has failed to find compatible matches for all components of the connection. It is, however, possible that the ICE agent did find compatible connections for some components.</td></tr><tr class="even"><td><code>"disconnected"</code></td><td>Checks to ensure that components are still connected failed for at least one component of the <a href="../rtcpeerconnection"><code>RTCPeerConnection</code></a>. This is a less stringent test than <code>"failed"</code> and may trigger intermittently and resolve just as spontaneously on less reliable networks, or during temporary disconnections. When the problem resolves, the connection may return to the <code>"connected"</code> state.</td></tr><tr class="odd"><td><code>"closed"</code></td><td>The ICE agent for this <a href="../rtcpeerconnection"><code>RTCPeerConnection</code></a> has shut down and is no longer handling requests.</td></tr></tbody></table>

Example
-------

    var pc = new RTCPeerConnection();
    var state = pc.iceConnectionState;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-peerconnection-ice-connection-state">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.iceConnectionState' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`iceConnectionState`

26

15

52

No

43

Promise-based version.

37-43

11

≤37

26

Yes

43

Promise-based version.

37-43

11

7.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   `iceconnectionstatechange`
-   [`RTCPeerConnection`](../rtcpeerconnection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceConnectionState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceConnectionState</a>
