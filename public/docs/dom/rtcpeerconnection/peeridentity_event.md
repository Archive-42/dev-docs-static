RTCPeerConnection: peeridentity event
=====================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `peeridentity` event is sent to the connection concerned when peer identity has been set and verified on it. The new identiy can be access using the [`RTCPeerConnection.peerIdentity`](peeridentity) property. An event handler for this event can be added via the [`RTCPeerConnection.onpeeridentity`](onpeeridentity) property.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onpeeridentity"><code>onpeeridentity</code></a></td></tr></tbody></table>

**Important:** This event and its event handler have been removed from the specification and are no longer available. Instead of using this event to detect when an identity is available, wait for the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by [`RTCPeerConnection.peerIdentity`](peeridentity) to be resolved. Once resolved, its value is the new identity.

Examples
--------

For the correct way to detect a new peer identity, see [`RTCPeerConnection.peerIdentity`](peeridentity).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-mediastream-peeridentity">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'peeridentity' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`peeridentity_event`

No

≤18-79

22

No

43

?

No

No

44

43

?

6.0

See also
--------

-   [WebRTC API](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/peeridentity_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/peeridentity_event</a>
