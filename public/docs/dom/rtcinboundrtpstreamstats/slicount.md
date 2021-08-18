RTCInboundRtpStreamStats.sliCount
=================================

The `sliCount` property of the [`RTCInboundRtpStreamStats`](../rtcinboundrtpstreamstats) dictionary indicates how many **Slice Loss Indication** (**SLI**) packets the [`RTCRtpReceiver`](../rtcrtpreceiver) for which this object provdes statistics sent to the remote [`RTCRtpSender`](../rtcrtpsender). An SLI packet is used by a decoder to let the encoder know that it's detected corruption of one or more consecutive macroblocks (in scan order) in the received media.

In general, what's usually of interest is that the higher this number is, the more the stream data is becoming corrupted between the sender and the receiver, requiring resends or dropping frames.

Syntax
------

    var sliCount = rtcInboundRtpStreamStats.sliCount;

### Value

An unsigned integer indicating the number of SLI packets this receiver sent to the remote sender due to lost runs of macroblocks. A high value of `sliCount` may be an indication of an unreliable network.

This is a very technical part of how video codecs work. For details, see [RFC 4585: 6.3.2](https://tools.ietf.org/html/rfc4585).

**Note:** This value is only present for video media.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcinboundrtpstreamstats-slicount">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCInboundRtpStreamStats.sliCount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCInboundRtpStreamStats.sliCount`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [RFC 4585: 6.3.2](https://tools.ietf.org/html/rfc4585): Definition of "Slice Loss Indication" in the document *Extended RTP Profile for Real-time Transport Control Protocol (RTCP)-Based Feedback (RTP/AVPF)*.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/sliCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/sliCount</a>
