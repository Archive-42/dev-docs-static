RTCIceCandidatePairStats.priority
=================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The *obsolete* [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) property `priority` reports the priority of the candidate pair as an integer value. The higher the value, the more likely the WebRTC layer is to select the candidate pair when the time comes to establish (or re-establish) a connection between the two peers.

Syntax
------

    pairPriority = rtcIceCandidatePairStats.priority;

### Value

An integer value indicating the priority of this pair of candidates as compared to other pairs on the same peer connection. The higher this value, the better the WebRTC layer thinks this pair of candidates is compared to the others, and the more likely a pair is to be selelcted for use.

**Note:** This property was removed from the specification as its value cannot be guaranteed to be accurately represented in a JavaScript number. You can calculcate its value using the algorithm described in [RFC 5245, section 5.7.2](https://tools.ietf.org/html/rfc5245#section-5.7.2) if you need this information and can accept the risk that the result may not be entirely accurate.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-priority">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.priority' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`priority`

No

No

42

29

No

?

?

No

No

42

29

?

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/priority" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/priority</a>
