RTCIceCandidateStats.transportId
================================

  
The [`RTCIceCandidateStats`](../rtcicecandidatestats) dictionary's `transportId` property is a string that uniquely identifies the transport that produced the <span class="page-not-created">`RTCTransportStats`</span> from which information about this candidate was taken.

Syntax
------

    transportID = rtcIceCandidateStats.transportId;

### Value

A [`DOMString`](../domstring) whose value uniquely identifies the transport from which any transport-related information accumulated in the [`RTCIceCandidateStats`](../rtcicecandidatestats) was taken. This can be used to compare candidates that would use the same transport, for example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatestats-transportid">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidateStats.transportId' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

31

No

?

?

No

No

31

?

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/transportId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/transportId</a>
