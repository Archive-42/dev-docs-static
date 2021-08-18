RTCIceCandidatePairStats.nominated
==================================

The [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) property `nominated` specifies whether or not the candidate pair described by the underlying `RTCIceCandidatePair` has been nominated to be used as the configuration for the WebRTC connection.

Syntax
------

    nominated = rtcIceCandidatePairStats.nominated;

### Value

A Boolean value which is set to `true` by the ICE layer if the controlling user agent has indicated that the candidate pair should be used to configure the WebRTC connection between the two peers.

**Note:** If more than one candidate pair are nominated at the same time, the one whose priority is higher will be selected for use.

Once a candidate pair has been nominated and the two peers have each reconfigured themselves to use the specified configuration, the ICE negotiation process can potentially end (or it can continue, to allow the connection to adapt to changing conditions).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-nominated">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.nominated' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`nominated`

No

No

56

No

?

?

No

No

56

?

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/nominated" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/nominated</a>
