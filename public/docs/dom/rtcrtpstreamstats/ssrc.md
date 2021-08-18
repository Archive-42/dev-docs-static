RTCRtpStreamStats.ssrc
======================

The [`RTCRtpStreamStats`](../rtcrtpstreamstats) dictionary's `ssrc` property provides the Synchronization Source (SSRC), an integer which uniquely identifies the source of the [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) packets whose statistics are covered by the [`RTCStatsReport`](../rtcstatsreport) that includes this `RTCRtpStreamStats` dictionary.

Syntax
------

    var ssrc = RTCRtpStreamStats.ssrc;

### Value

The Synchronization Source (SSRC) is a 32-bit integer uniquely identifying the source of the RTP packets whose statistics are covered by the [`RTCStatsReport`](../rtcstatsreport) object of which this `RTCRtpStreamStats` object is a component.

The manner in which these values are generated is not mandated by the specification, although it does make recommendations. You should not make any assumptions based on the value of `ssrc` other than that any two objects with the same `ssrc` value refer to the same source. See [RFC 3550, section 8](https://tools.ietf.org/html/rfc3550#section-8) for additional information about `ssrc`.

**Note:** The specification includes an example that generates values for `ssrc` using MD5. While not part of the standard, exactly, it is a good mechanism that may be used by some browsers; others may use other methods, such as random number generators. *Do not* rely upon these values meaning anything other than "these objects are associated with the same source."

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcrtpstreamstats-ssrc">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCRtpStreamStats.ssrc' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ssrc`

No

No

27

No

No

?

No

No

27

No

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/ssrc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/ssrc</a>
