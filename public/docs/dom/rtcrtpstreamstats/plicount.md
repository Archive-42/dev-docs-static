RTCRtpStreamStats.pliCount
==========================

The `pliCount` property of the [`RTCRtpStreamStats`](../rtcrtpstreamstats) dictionary states the number of times the stream's receiving end sent a **Picture Loss Indication** (**PLI**) packet to the sender. A PLI packet indicates that some amount of encoded video data has been lost for one or more frames.

Syntax
------

    var pliCount = RTCRtpStreamStats.pliCount;

### Value

An integer value indicating the number of times a PLI packet was sent by the stream's receiver to the sender.

A PLI message is used by video decoders (running on the receiving end of the stream) to notify the encoder (the sender) that an undefined amount of coded video data, which may span frame boundaries, has been lost.

This may trigger the sender to send a full frame in order to allow the receiver to re-synchronize, since lost data may be an irrecoverable situation for decoding media. However, the primary purpose of this message is to allow the sender to consider techniques to mitigate network performance issues. This is often achieved by methods such as increasing the compression, lowering resolution, or finding other ways to reduce the bit rate of the stream.

**Note:** This value is only available on the receiver, and only for video media.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcinboundrtpstreamstats-plicount">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCInboundRtpStreamStats: pliCount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcoutboundrtpstreamstats-plicount">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCOutboundRtpStreamStats: pliCount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`pliCount`

No

No

55

No

No

?

No

No

55

No

?

No

See also
--------

-   [RFC 4585: 6.3.1](https://tools.ietf.org/html/rfc4585): Definition of "PLI messages" in the document *Extended RTP Profile for Real-time Transport Control Protocol (RTCP)-Based Feedback (RTP/AVPF)*.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/pliCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/pliCount</a>
