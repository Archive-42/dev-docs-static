RTCRtpStreamStats.sliCount
==========================

The `sliCount` property of the [`RTCRtpStreamStats`](../rtcrtpstreamstats) dictionary indicates how many **Slice Loss Indication** (**SLI**) packets were received by the sender. An SLI packet is used by a decoder to let the encoder know that it's detected corruption of one or more consecutive macroblocks in the received media.

Syntax
------

    var sliCount = RTCRtpStreamStats.sliCount;

### Value

An unsigned long integer indicating the number of SLI packets the sender received from the receiver due to lost runs of macroblocks. A high value of `sliCount` may be an indication of an unreliable network.

For technical details, see [RFC 4585: 6.3.2](https://tools.ietf.org/html/rfc4585).

**Note:** This value is sent by the sender to the receiver and is only present for video media.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcinboundrtpstreamstats-slicount">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCInboundRtpStreamStats: sliCount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcoutboundrtpstreamstats-slicount">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCOutboundRtpStreamStats: sliCount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`sliCount`

No

No

No

No

No

?

No

No

No

No

?

No

See also
--------

-   [RFC 4585: 6.3.2](https://tools.ietf.org/html/rfc4585): Definition of "Slice Loss Indication" in the document *Extended RTP Profile for Real-time Transport Control Protocol (RTCP)-Based Feedback (RTP/AVPF)*.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/sliCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/sliCount</a>
