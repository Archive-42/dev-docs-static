RTCStatsReport
==============

**Draft**

This page is not complete.

*This page is currently incomplete and under active construction. Please be aware that it's not going to answer all of your questions just yet.*

The `RTCStatsReport` interface provides a statistics report obtained by calling one of the [`RTCPeerConnection.getStats()`](rtcpeerconnection/getstats), [`RTCRtpReceiver.getStats()`](rtcrtpreceiver/getstats), and [`RTCRtpSender.getStats()`](rtcrtpsender/getstats) methods. This statistics report contains a mapping of statistic category string names to objects containing the corresponding statistics data.

Calling `getStats()` on an [`RTCPeerConnection`](rtcpeerconnection) lets you specify whether you wish to obtain statistics for outbound, inbound, or all streams on the connection. The [`RTCRtpReceiver`](rtcrtpreceiver) and [`RTCRtpSender`](rtcrtpsender) versions of `getStats()` specifically only return statistics available to the incoming or outgoing stream on which you call them.

The statistics objects
----------------------

For each category of statistic information, there is a dictionary whose properties provide the relevant information.

### Properties common to all statistic categories

All WebRTC statistics objects are fundamentally based on the [`RTCStats`](rtcstats) dictionary, which provides the most fundamental information: the timestamp, the statistic type string, and an ID uniquely identifying the source of the data:

[`id`](rtcstats/id)  
A [`DOMString`](domstring) which uniquely identifies the object which was inspected to produce this object based on `RTCStats`.

[`timestamp`](rtcstats/timestamp)  
A [`DOMHighResTimeStamp`](domhighrestimestamp) object indicating the time at which the sample was taken for this statistics object.

[`type`](rtcstats/type)  
A [`DOMString`](domstring) indicating the type of statistics the object contains, taken from the enum type [`RTCStatsType`](rtcstatstype).

### The statistic categories

The [`type`](rtcstats/type) gives the name of the statistic category represented by the object, and is how you locate the specific type of data you need. The statistic category names are members of the enumerated type [`RTCStatsType`](rtcstatstype), as follows:

`candidate-pair`  
An [`RTCIceCandidatePairStats`](rtcicecandidatepairstats) object providing statistics related to an [`RTCIceTransport`](rtcicetransport). Candidate pairs other than the currently active pair for the transport are deleted when the [`RTCPeerConnection`](rtcpeerconnection) changes its [`RTCPeerConnection.iceGatheringState`](rtcpeerconnection/icegatheringstate) to `new` during an [ICE restart](webrtc_api/session_lifetime#ice_restart). The active candidate pair is deleted after the transport switches to another candidate pair; this change cannot be detected otherwise.

`certificate`  
An <span class="page-not-created">`RTCCertificateStats`</span> object providing statistics related to a certificate being used by an [`RTCIceTransport`](rtcicetransport).

`codec`  
An <span class="page-not-created">`RTCCodecStats`</span> object containing statistics about a codec currently being used by [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) streams to send or receive data for the [`RTCPeerConnection`](rtcpeerconnection).

`csrc`  
An <span class="page-not-created">`RTCContributingSourceStats`</span> object which contains statistics related to a contributing source (CSRC) that contributed to an inbound RTP stream.

`data-channel`  
An <span class="page-not-created">`RTCDataChannelStats`</span> object which contains statistics about each [`RTCDataChannel`](rtcdatachannel) on the connection.

`inbound-rtp`  
An [`RTCInboundRtpStreamStats`](rtcinboundrtpstreamstats) object providing statistics about *inbound* data being received from remote peers. Since this only provides statistics related to inbound data, without considering the local peer's state, any values that require knowledge of both, such as round-trip time, is not included. This report isn't available if there are no connected peers.

`local-candidate`  
An [`RTCIceCandidateStats`](rtcicecandidatestats) object giving statistics about an ICE local candidate; these candidates are found in the output from [`RTCIceTransport.getLocalCandidates()`](rtcicetransport/getlocalcandidates).

`outbound-rtp`  
The report is an [`RTCOutboundRtpStreamStats`](rtcoutboundrtpstreamstats) object providing statistics based on the local peer's *outgoing* data being sent to its peers. This information considers only the outbound RTP stream, so any data which requires information about the state of the remote peers (such as round-trip time) is unavailable, since those values can't be computed without knowing about the other peers' states.

`peer-connection`  
A <span class="page-not-created">`RTCPeerConnectionStats`</span> object provides statistics related to the overall peer connection's [`RTCPeerConnection`](rtcpeerconnection).

`receiver`  
Provides statistics about a specific [`RTCRtpReceiver`](rtcrtpreceiver). The statistics object is an <span class="page-not-created">`RTCAudioReceiverStats`</span> object if <span class="page-not-created">`kind`</span> is `audio`; if `kind` is `video`, the object is an <span class="page-not-created">`RTCVideoReceiverStats`</span> object.

`remote-candidate`  
The report is an [`RTCIceCandidateStats`](rtcicecandidatestats) object containing statistics about the remote candidate's [`RTCIceTransport`](rtcicetransport). This may include information such as the type of network, the protocol, the URL, the type of relay being used, and so forth.

`remote-inbound-rtp`  
The report is an <span class="page-not-created">`RTCRemoteInboundRtpStreamStats`</span> object providing statistics about your outbound RTP data stream, but from the perspective of the remote peer. That is, this information is about your `outbound-rtp` stream, but as seen by the remote device that's handling the stream. You can use this information to do things like determine how well the remote peer is receiving data.

`remote-outbound-rtp`  
The report is an [`RTCRemoteOutboundRtpStreamStats`](rtcremoteoutboundrtpstreamstats) object that contains statistics about your inbound RTP (`inbound-rtp`) stream, but from the perspective of the remote peer.

`sender`  
An object containing statistics about the [`RTCRtpSender`](rtcrtpsender) for a stream on the [`RTCPeerConnection`](rtcpeerconnection). If <span class="page-not-created">`kind`</span> is `"audio"`, this object is of type <span class="page-not-created">`RTCAudioSenderStats`</span>; if `kind` is `"video"`, this is an <span class="page-not-created">`RTCVideoSenderStats`</span> object.

`stream`  
An object of type <span class="page-not-created">`RTCMediaStreamStats`</span>, providing statistics and information about a [`MediaStream`](mediastream) which is part of the [`RTCPeerConnection`](rtcpeerconnection).

`track`  
The object is one of the types based on <span class="page-not-created">`RTCMediaHandlerStats`</span>: for audio tracks, the type is <span class="page-not-created">`RTCSenderAudioTrackAttachmentStats`</span> and for video tracks, the type is <span class="page-not-created">`RTCSenderVideoTrackAttachmentStats`</span>. The data within provides statistics related to a particular [`MediaStreamTrack`](mediastreamtrack)'s attachment to an [`RTCRtpSender`](rtcrtpsender); also included are the media level metrics that go along with the track.

`transport`  
An object that contains statistics related to a transport for an `RTCPeerConnection`. The object is of type <span class="page-not-created">`RTCTransportStats`</span>.

Using RTCStatsReport
--------------------

*... coming soon-ish ...*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcstatsreport-object">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCStatsReport' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`RTCStatsReport`

58

79

27

No

45

11

58

58

27

43

11

7.0

`entries`

58

79

48

No

45

11

58

58

48

43

11

7.0

`forEach`

58

79

27

No

45

11

58

58

27

43

11

7.0

`get`

58

79

27

No

45

11

58

58

27

43

11

7.0

`has`

58

79

27

No

45

11

58

58

27

43

11

7.0

`keys`

58

79

48

No

45

11

58

58

48

43

11

7.0

`size`

59

79

48

No

46

11

59

59

48

43

11

7.0

`values`

58

79

48

No

45

11

58

58

48

43

11

7.0

See also
--------

-   [WebRTC API](webrtc_api)
-   [`RTCPeerConnection`](rtcpeerconnection)
-   [`RTCPeerConnection.getStats()`](rtcpeerconnection/getstats), [`RTCRtpReceiver.getStats()`](rtcrtpreceiver/getstats), and [`RTCRtpSender.getStats()`](rtcrtpsender/getstats)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport</a>
