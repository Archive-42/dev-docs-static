RTCPeerConnection.signalingState
================================

The read-only `signalingState` property on the [`RTCPeerConnection`](../rtcpeerconnection) interface returns one of the string values specified by the `RTCSignalingState` enum; these values describe the state of the signaling process on the local end of the connection while connecting or reconnecting to another peer. See [Signaling](../webrtc_api/session_lifetime#signaling) in [Lifetime of a WebRTC session](../webrtc_api/session_lifetime) for more details about the signaling process.

Because the signaling process is a state machine, being able to verify that your code is in the expected state when messages arrive can help avoid unexpected and avoidable failures. For example, if you receive an answer while the `signalingState` isn't `"have-local-offer"`, you know that something is wrong, since you should only receive answers after creating an offer but before an answer has been received and passed into [`RTCPeerConnection.setLocalDescription()`](setlocaldescription). Your code will be more reliable if you watch for mismatched states like this and handle them gracefully.

This value may also be useful during debugging, for example.

In addition, when the value of this property changes, a `signalingstatechange` event is sent to the [`RTCPeerConnection`](../rtcpeerconnection) instance.

Syntax
------

     var state = RTCPeerConnection.signalingState;

### Value

The allowed values are those included in the enum `RTCSignalingState`.

### RTCSignalingState enum

The `RTCSignalingState` enum specifies the possible values of [`RTCPeerConnection.signalingState`](signalingstate), which indicates where in the process of signaling the exchange of offer and answer the connection currently is.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>"stable"</code></td><td>There is no ongoing exchange of offer and answer underway. This may mean that the <a href="../rtcpeerconnection"><code>RTCPeerConnection</code></a> object is new, in which case both the <a href="localdescription"><code>localDescription</code></a> and <a href="remotedescription"><code>remoteDescription</code></a> are <code>null</code>; it may also mean that negotiation is complete and a connection has been established.</td></tr><tr class="even"><td><code>"have-local-offer"</code></td><td>The local peer has called <a href="setlocaldescription"><code>RTCPeerConnection.setLocalDescription()</code></a>, passing in SDP representing an offer (usually created by calling <a href="createoffer"><code>RTCPeerConnection.createOffer()</code></a>), and the offer has been applied successfully.</td></tr><tr class="odd"><td><code>"have-remote-offer"</code></td><td>The remote peer has created an offer and used the signaling server to deliver it to the local peer, which has set the offer as the remote description by calling <a href="setremotedescription"><code>RTCPeerConnection.setRemoteDescription()</code></a>.</td></tr><tr class="even"><td><code>"have-local-pranswer"</code></td><td>The offer sent by the remote peer has been applied and an answer has been created (usually by calling <a href="createanswer"><code>RTCPeerConnection.createAnswer()</code></a>) and applied by calling <a href="setlocaldescription"><code>RTCPeerConnection.setLocalDescription()</code></a>. This provisional answer describes the supported media formats and so forth, but may not have a complete set of ICE candidates included. Further candidates will be delivered separately later.</td></tr><tr class="odd"><td><code>"have-remote-pranswer"</code></td><td>A provisional answer has been received and successfully applied in response to an offer previously sent and established by calling <code>setLocalDescription()</code>.</td></tr><tr class="even"><td><code>"closed"</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><p>The connection is closed.</p><div class="note notecard"><p><strong>Note:</strong> This value moved into the <a href="#rtcpeerconnectionstate_enum"><code>RTCPeerConnectionState</code> enum</a> in the May 13, 2016 draft of the specification, as it reflects the state of the <code>RTCPeerConnection</code>, not the signaling connection. You now detect a closed connection by checking for <a href="connectionstate"><code>connectionState</code></a> to be <code>"closed"</code> instead.</p></div></td></tr></tbody></table>

Example
-------

    var pc = new RTCPeerConnection(configuration);
    var state = pc.signalingState;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-peerconnection-signaling-state">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.signalingState' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`signalingState`

26

15

22

No

43

Promise-based version.

37-43

11

≤37

26

44

43

Promise-based version.

37-43

11

6.0

See also
--------

-   [Lifetime of a WebRTC session](../webrtc_api/session_lifetime)
-   [`RTCPeerConnection`](../rtcpeerconnection)
-   `signalingstatechange`
-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/signalingState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/signalingState</a>
