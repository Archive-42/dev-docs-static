RTCOutboundRtpStreamStats.pliCount
==================================

The `pliCount` property of the [`RTCOutboundRtpStreamStats`](../rtcoutboundrtpstreamstats) dictionary states the number of times the remote peer's [`RTCRtpReceiver`](../rtcrtpreceiver) sent a **Picture Loss Indication** (**PLI**) packet to the [`RTCRtpSender`](../rtcrtpsender) for which this object provides statistics. A PLI packet indicates that some amount of encoded video data has been lost for one or more frames.

Syntax
------

    var pliCount = RTCOutboundRtpStreamStats.pliCount;

### Value

An integer value indicating the number of times a PLI packet was sent to this sender by the remote peer's [`RTCRtpReceiver`](../rtcrtpreceiver). These are sent by the receiver's decoder to notify the sender's encoder that an undefined amount of coded video data, which may span frame boundaries, has been lost.

**Note:** This property is only used for video streams.

Usage notes
-----------

Upon receiving a PLI packet, the sender may have responded by sending a full frame to the remote peer to allow it to re-synchronize with the media. However, the primary purpose of a PLI packet is to allow the `RTCRtpSender` for which this `RTCOutboundRtpStreamStats` object provides statistics to consider techniques to mitigate network performance issues. This is often achieved by methods such as increasing the compression or lowering resolution, although the mechanisms available to reduce the bit rate of the stream vary from codec to codec.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-RTCOutboundRtpStreamStats-plicount">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCOutboundRtpStreamStats.pliCount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCOutboundRtpStreamStats.pliCount`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [RFC 4585: 6.3.1](https://tools.ietf.org/html/rfc4585): Definition of "PLI messages" in the document *Extended RTP Profile for Real-time Transport Control Protocol (RTCP)-Based Feedback (RTP/AVPF)*.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats/pliCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats/pliCount</a>
