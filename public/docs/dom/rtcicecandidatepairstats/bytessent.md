RTCIceCandidatePairStats.bytesSent
==================================

The [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) property `bytesSent` indicates the total number of payload bytes—that is, bytes which aren't overhead such as headers or padding—that hve been sent so far on the connection described by the candidate pair.

The [`bytesReceived`](bytesreceived) property reports the number of bytes received so far on the described connection.

Syntax
------

    sent = rtcIceCandidatePairStats.bytesSent;

### Value

An integer value indicating the total number of bytes sent so far on the connection described by this candidate pair. Only data bytes are counted; overhead such as padding, headers, and the like are not included in this count.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-bytessent">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.bytesSent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`bytesSent`

Yes

≤79

56

No

?

?

Yes

Yes

56

?

?

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/bytesSent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/bytesSent</a>
