RTCPeerConnection: idpvalidationerror event
===========================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

An `idpvalidationerror` event informs the target, a [`RTCPeerConnection`](rtcpeerconnection) object, that the identity provider (IdP) encountered an error when trying to validate an identity assertion. An event handler for this event can be added via the [`RTCPeerConnection.onidpvalidationerror`](rtcpeerconnection/onidpvalidationerror) property.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="rtcidentityerrorevent"><code>RTCIdentityErrorEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="rtcpeerconnection/onidpvalidationerror"><code>onidpvalidationerror</code></a></td></tr></tbody></table>

**Important:** This event is no longer used; it was removed from the specification long ago. Instead, you should watch for the [`RTCPeerConnection.peerIdentity`](rtcpeerconnection/peeridentity) [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to be rejected with an `OperationError`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-mediastream-idpvalidationerror">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'idpvalidationerror' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCPeerConnection_idpvalidationerror_event`

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

-   [WebRTC API](webrtc_api)
-   `idpassertionerror`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection_idpvalidationerror_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection_idpvalidationerror_event</a>
