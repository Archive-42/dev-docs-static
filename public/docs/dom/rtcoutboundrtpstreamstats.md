RTCOutboundRtpStreamStats
=========================

The `RTCOutboundRtpStreamStats` dictionary is the [`RTCStats`](rtcstats)-based object which provides metrics and statistics related to an outbound [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) stream being sent by an [`RTCRtpSender`](rtcrtpsender).

Properties
----------

*The `RTCOutboundRtpStreamStats` dictionary includes the following properties in addition to those it inherits from <span class="page-not-created">`RTCSentRtpStreamStats`</span>, [`RTCRtpStreamStats`](rtcrtpstreamstats), and [`RTCStats`](rtcstats).*

[`averageRtcpInterval`](rtcoutboundrtpstreamstats/averagertcpinterval)  
A floating-point value indicating the average [RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP) interval between two consecutive compound RTCP packets.

[`firCount`](rtcoutboundrtpstreamstats/fircount)  
An integer value which indicates the total number of Full Intra Request (FIR) packets which this [`RTCRtpSender`](rtcrtpsender) has sent to the remote [`RTCRtpReceiver`](rtcrtpreceiver). This is an indicator of how often the stream has lagged, requiring frames to be skipped in order to catch up. *Valid only for video streams.*

[`framesEncoded`](rtcoutboundrtpstreamstats/framesencoded)  
The number of frames that have been successfully encoded so far for sending on this RTP stream. *Only valid for video streams.*

[`lastPacketSentTimestamp`](rtcoutboundrtpstreamstats/lastpacketsenttimestamp)  
A [`DOMHighResTimeStamp`](domhighrestimestamp) indicating the time at which the last packet was sent for this SSRC. The [`timestamp`](rtcstats/timestamp) property, on the other hand, indicates the time at which the `RTCOutboundRtpStreamStats` object was generated.

[`nackCount`](rtcoutboundrtpstreamstats/nackcount)  
An integer value indicating the total number of Negative ACKnolwedgement (NACK) packets this `RTCRtpSender` has received from the remote [`RTCRtpReceiver`](rtcrtpreceiver).

[`perDscpPacketsSent`](rtcoutboundrtpstreamstats/perdscppacketssent)  
A record of key-value pairs with strings as the keys mapped to 32-bit integer values, each indicating the total number of packets this `RTCRtpSender` has transmitted for this source for each Differentiated Services Code Point (DSCP).

[`pliCount`](rtcoutboundrtpstreamstats/plicount)  
An integer specifying the number of times the remote receiver has notified this `RTCRtpSender` that some amount of encoded video data for one or more frames has been lost, using Picture Loss Indication (PLI) packets. *Only available for video streams.*

[`qpSum`](rtcoutboundrtpstreamstats/qpsum)  
A 64-bit value containing the sum of the QP values for every frame encoded by this [`RTCRtpSender`](rtcrtpsender). *Valid only for video streams.*

<span class="page-not-created">`qualityLimitationDurations`</span>  
A record mapping each of the quality limitation reasons in the <span class="page-not-created">`RTCRemoteInboundRtpStreamStats`</span> enumeration to a floating-point value indicating the number of seconds the stream has spent with its quality limited for that reason.

[`qualityLimitationReason`](rtcoutboundrtpstreamstats/qualitylimitationreason)  
A value from the <span class="page-not-created">`RTCQualityLimitationReason`</span> enumerated type explaining why the resolution and/or frame rate is being limited for this RTP stream. *Valid only for video streams*.

[`remoteId`](rtcoutboundrtpstreamstats/remoteid)  
A string which identifies the <span class="page-not-created">`RTCRemoteInboundRtpStreamStats`</span> object that provides statistics for the remote peer for this same SSRC. This ID is stable across multiple calls to `getStats()`.

<span class="page-not-created">`retransmittedBytesSent`</span>  
The total number of bytes that have been retransmitted for this source as of the time the statistics were sampled. These retransmitted bytes comprise the packets included in the value returned by <span class="page-not-created">`retransmittedPacketsSent`</span>.

<span class="page-not-created">`retransmittedPacketsSent`</span>  
The total number of packets that have needed to be retransmitted for this source as of the time the statistics were sampled. These retransmitted packets are included in the value returned by <span class="page-not-created">`packetsSent`</span>.

<span class="page-not-created">`senderId`</span>  
The [`id`](rtcstats/id) of the <span class="page-not-created">`RTCAudioSenderStats`</span> or <span class="page-not-created">`RTCVideoSenderStats`</span> object containing statistics about this stream's [`RTCRtpSender`](rtcrtpsender).

[`sliCount`](rtcoutboundrtpstreamstats/slicount)  
An integer indicating the number of times this sender received a Slice Loss Indication (SLI) frame from the remote peer, indicating that one or more consecutive video macroblocks have been lost or corrupted. Available only for video streams.

<span class="page-not-created">`targetBitrate`</span>  
A value indicating the bit rate the `RTCRtpSender`'s codec is configured to attempt to achieve in its output media.

<span class="page-not-created">`totalEncodedBytesTarget`</span>  
A cumulative sum of the *target* frame sizes (the targeted maximum size of the frame in bytes when the codec is asked to compress it) for all of the frames encoded so far. This will likely differ from the total of the *actual* frame sizes.

<span class="page-not-created">`totalEncodeTime`</span>  
A floating-point value indicating the total number of seconds that have been spent encoding the frames encoded so far by this [`RTCRtpSender`](rtcrtpsender).

[`trackId`](rtcoutboundrtpstreamstats/trackid)  
The [`id`](rtcstats/id) of the <span class="page-not-created">`RTCSenderAudioTrackAttachmentStats`</span> or <span class="page-not-created">`RTCSenderVideoTrackAttachmentStats`</span> object containing the current track attachment to the [`RTCRtpSender`](rtcrtpsender) responsible for this stream.

Examples
--------

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#outboundrtpstats-dict*">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCOutboundRtpStreamStats' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCOutboundRtpStreamStats`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`RTCStats`](rtcstats)
-   [`RTCStatsReport`](rtcstatsreport)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats</a>
