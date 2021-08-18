RTCPeerConnection.connectionState
=================================

The read-only `connectionState` property of the [`RTCPeerConnection`](../rtcpeerconnection) interface indicates the current state of the peer connection by returning one of the string values specified by the enum `RTCPeerConnectionState`.

When this property's value changes, a `connectionstatechange` event is sent to the [`RTCPeerConnection`](../rtcpeerconnection) instance.

Syntax
------

    var connectionState = RTCPeerConnection.connectionState;

### Value

The current state of the connection, as a value from the enum `RTCPeerConnectionState`.

### RTCPeerConnectionState enum

The `RTCPeerConnectionState` enum defines string constants which describe states in which the `RTCPeerConnection` may be. These values are returned by the [`connectionState`](connectionstate) property. This state essentially represents the aggregate state of all ICE transports (which are of type [`RTCIceTransport`](../rtcicetransport) or [`RTCDtlsTransport`](../rtcdtlstransport)) being used by the connection.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>"new"</code></td><td>At least one of the connection's ICE transports (<a href="../rtcicetransport"><code>RTCIceTransport</code></a>s or <a href="../rtcdtlstransport"><code>RTCDtlsTransport</code></a>s) are in the <code>"new"</code> state, and none of them are in one of the following states: <code>"connecting"</code>, <code>"checking"</code>, <code>"failed"</code>, or <code>"disconnected"</code>, <em>or</em> all of the connection's transports are in the <code>"closed"</code> state.</td></tr><tr class="even"><td><code>"connecting"</code></td><td>One or more of the ICE transports are currently in the process of establishing a connection; that is, their <code>RTCIceConnectionState</code> is either <code>"checking"</code> or <code>"connected"</code>, and no transports are in the <code>"failed"</code> state. <strong>&lt;&lt;&lt; Make this a link once I know where that will be documented</strong></td></tr><tr class="odd"><td><code>"connected"</code></td><td>Every ICE transport used by the connection is either in use (state <code>"connected"</code> or <code>"completed"</code>) or is closed (state <code>"closed"</code>); in addition, at least one transport is either <code>"connected"</code> or <code>"completed"</code>.</td></tr><tr class="even"><td><code>"disconnected"</code></td><td>At least one of the ICE transports for the connection is in the <code>"disconnected"</code> state and none of the other transports are in the state <code>"failed"</code>, <code>"connecting"</code>, or <code>"checking"</code>.</td></tr><tr class="odd"><td><code>"failed"</code></td><td>One or more of the ICE transports on the connection is in the <code>"failed"</code> state.</td></tr><tr class="even"><td><code>"closed"</code></td><td><p>The <code>RTCPeerConnection</code> is closed.</p><p>This value was in the <a href="#rtcsignalingstate_enum"><code>RTCSignalingState</code> enum</a> (and therefore found by reading the value of the <a href="signalingstate"><code>signalingState</code></a>) property until the May 13, 2016 draft of the specification.</p></td></tr></tbody></table>

Example
-------

    var pc = new RTCPeerConnection(configuration);

    /* ... */

    var connectionState = pc.connectionState;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-peerconnection-connection-state">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.connectionState' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`connectionState`

72

79

No

No

No

11

72

72

No

No

11

11.0

See also
--------

-   [Lifetime of a WebRTC session](../webrtc_api/session_lifetime)
-   [`RTCPeerConnection`](../rtcpeerconnection)
-   `connectionstatechange`
-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/connectionState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/connectionState</a>
