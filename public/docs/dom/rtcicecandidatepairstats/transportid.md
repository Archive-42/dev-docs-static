RTCIceCandidatePairStats.transportId
====================================

The `transportId` property uniquely identifies the [`RTCIceTransport`](../rtcicetransport) that was inspected to obtain the transport-related statistics contained in the [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) object.

Syntax
------

    transportId = rtcIceCandidatePairStats.transportId;

### Value

A [`DOMString`](../domstring) which uniquely identifies the `RTCIceTransport` object from which the transport-related data was obtained for the statistics contained in this [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) object.

The transport-related statistics come from the <span class="page-not-created">`RTCTransportStats`</span> dictionary's properties.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-transportid">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.transportId' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`transportId`

No

No

56

29

No

?

?

No

No

56

29

?

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/transportId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/transportId</a>
