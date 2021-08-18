RTCInboundRtpStreamStats.pliCount
=================================

The `pliCount` property of the [`RTCInboundRtpStreamStats`](../rtcinboundrtpstreamstats) dictionary states the number of times the [`RTCRtpReceiver`](../rtcrtpreceiver) described by these statistics sent a **Picture Loss Indication** (**PLI**) packet to the sender. A PLI packet indicates that some amount of encoded video data has been lost for one or more frames.

Syntax
------

    var pliCount = RTCInboundRtpStreamStats.pliCount;

### Value

An integer value indicating the number of times a PLI packet was sent by the [`RTCRtpReceiver`](../rtcrtpreceiver) to the sender. These are sent by the receiver's decoder to notify the encoder (the sender) that an undefined amount of coded video data, which may span frame boundaries, has been lost. This information is only available for video streams.

This may trigger the sender to send a full frame in order to allow the receiver to re-synchronize, since lost data may be an irrecoverable situation for decoding media. However, the primary purpose of this message is to allow the sender to consider techniques to mitigate network performance issues. This is often achieved by methods such as increasing the compression, lowering resolution, or finding other ways to reduce the bit rate of the stream.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcinboundrtpstreamstats-plicount">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCInboundRtpStreamStats.pliCount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCInboundRtpStreamStats.pliCount`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [RFC 4585: 6.3.1](https://tools.ietf.org/html/rfc4585): Definition of "PLI messages" in the document *Extended RTP Profile for Real-time Transport Control Protocol (RTCP)-Based Feedback (RTP/AVPF)*.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/pliCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/pliCount</a>
