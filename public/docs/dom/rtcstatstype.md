RTCStatsType
============

The `RTCStatsType` enumerated type (enum) is a set of strings which define the [`type`](rtcstats/type) of statistics reported in a record found in the [`RTCStatsReport`](rtcstatsreport) object. This type determines which of the [`RTCStats`](rtcstats)-based dictionaries the record is based upon.

Values
------

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcstatstype">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCStatsType' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCStatsType`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsType</a>
