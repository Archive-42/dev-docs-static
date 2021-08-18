RTCInboundRtpStreamStats
========================

The [WebRTC API](webrtc_api)'s `RTCInboundRtpStreamStats` dictionary, based upon <span class="page-not-created">`RTCReceivedRtpStreamStats`</span> and [`RTCStats`](rtcstats), contains statistics related to the receiving end of an RTP stream on the local end of the [`RTCPeerConnection`](rtcpeerconnection).

Properties
----------

The `RTCInboundRtpStreamStats` dictionary is based on the <span class="page-not-created">`RTCReceivedRtpStreamStats`</span> dictionary, whose properties are also available.

[`averageRtcpInterval`](rtcinboundrtpstreamstats/averagertcpinterval)  
A floating-point value indicating the average [RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP) interval between two consecutive compound RTCP packets.

[`bytesReceived`](rtcinboundrtpstreamstats/bytesreceived)  
A 64-bit integer which indicates the total number of bytes that have been received so far for this media source.

[`fecPacketsDiscarded`](rtcinboundrtpstreamstats/fecpacketsdiscarded)  
An integer value indicating the number of RTP Forward Error Correction (FEC) packets which have been received for this source, for which the error correction payload was discarded.

[`fecPacketsReceived`](rtcinboundrtpstreamstats/fecpacketsreceived)  
An integer value indicating the total number of RTP FEC packets received for this source. This counter may also be incremented when FEC packets arrive in-band along with media content; this can happen with Opus, for example.

[`firCount`](rtcinboundrtpstreamstats/fircount)  
An integer value which indicates the total number of Full Intra Request (FIR) packets which this receiver has sent to the sender. This is an indicator of how often the stream has lagged, requiring frames to be skipped in order to catch up. This value is only available for video streams.

[`framesDecoded`](rtcinboundrtpstreamstats/framesdecoded)  
A long integer value indicating the total number of frames of video which have been correctly decoded so far for this media source. This is the number of frames that would have been rendered if none were dropped. *Only valid for video streams.*

[`lastPacketReceivedTimestamp`](rtcinboundrtpstreamstats/lastpacketreceivedtimestamp)  
A [`DOMHighResTimeStamp`](domhighrestimestamp) indicating the time at which the last packet was received for this source. The [`timestamp`](rtcstats/timestamp) property, on the other hand, indicates the time at which the statistics object was generated.

[`nackCount`](rtcinboundrtpstreamstats/nackcount)  
An integer value indicating the total number of Negative ACKnolwedgement (NACK) packets this receiver has sent.

[`packetsDuplicated`](rtcinboundrtpstreamstats/packetsduplicated)  
An integer value indicating the total number of packets that have been discarded because they were duplicates. These packets are not counted by <span class="page-not-created">`packetsDiscarded`</span>.

[`packetsFailedDecryption`](rtcinboundrtpstreamstats/packetsfaileddecryption)  
An integer totaling the number of RTP packets that could not be decrypted. These packets are not counted by <span class="page-not-created">`packetsDiscarded`</span>.

[`perDscpPacketsReceived`](rtcinboundrtpstreamstats/perdscppacketsreceived)  
A record of key-value pairs with strings as the keys mapped to 32-bit integer values, each indicating the total number of packets this receiver has received on this RTP stream from this source for each Differentiated Services Code Point (DSCP).

[`pliCount`](rtcinboundrtpstreamstats/plicount)  
An integer specifying the number of times the receiver has notified the sender that some amount of encoded video data for one or more frames has been lost, using Picture Loss Indication (PLI) packets. This is only available for video streams.

[`qpSum`](rtcinboundrtpstreamstats/qpsum)  
A 64-bit value containing the sum of the QP values for every frame decoded by this RTP receiver. You can determine the average QP per frame by dividing this value by [`framesDecoded`](rtcinboundrtpstreamstats/framesdecoded). *Valid only for video streams.*

[`receiverId`](rtcinboundrtpstreamstats/receiverid)  
A string indicating which identifies the <span class="page-not-created">`RTCAudioReceiverStats`</span> or <span class="page-not-created">`RTCVideoReceiverStats`</span> object associated with the stream's receiver. This ID is stable across multiple calls to `getStats()`.

[`remoteId`](rtcinboundrtpstreamstats/remoteid)  
A string which identifies the [`RTCRemoteOutboundRtpStreamStats`](rtcremoteoutboundrtpstreamstats) object that provides statistics for the remote peer for this same SSRC. This ID is stable across multiple calls to `getStats()`.

[`sliCount`](rtcinboundrtpstreamstats/slicount)  
An integer indicating the number of times the receiver sent a Slice Loss Indication (SLI) frame to the sender to tell it that one or more consecutive (in terms of scan order) video macroblocks have been lost or corrupted. Available only for video streams.

[`trackId`](rtcinboundrtpstreamstats/trackid)  
A string which identifies the statistics object representing the receiving track; this object is one of two types: <span class="page-not-created">`RTCReceiverAudioTrackAttachmentStats`</span> or <span class="page-not-created">`RTCReceiverVideoTrackAttachmentStats`</span>. This ID is stable across multiple calls to `getStats()`.

Examples
--------

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#inboundrtpstats-dict*">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCInboundRtpStreamStats' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCInboundRtpStreamStats`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`RTCStats`](rtcstats)
-   [`RTCStatsReport`](rtcstatsreport)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats</a>
