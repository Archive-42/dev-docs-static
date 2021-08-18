RTCRtpStreamStats
=================

The [`RTCRtpStreamStats`](rtcrtpstreamstats) dictionary is returned by the [`RTCPeerConnection.getStats()`](rtcpeerconnection/getstats), [`RTCRtpSender.getStats()`](rtcrtpsender/getstats), and [`RTCRtpReceiver.getStats()`](rtcrtpreceiver/getstats) methods to provide detailed statistics about WebRTC connectivity. While the dictionary has a base set of properties that are present in each of these cases, there are also additional properties added depending on which interface the method is called on.

`RTCRtpStreamStats` is the base class for all RTP-related statistics reports. It's based on [RTCStats](#rtcstats) and adds the following additional fields.

**Note:** This interface was called `RTCRTPStreamStats` until a specification update in the spring of 2017. Check the [Browser compatibility](#browser_compatibility) table to know if and when the name change was implemented in specific browsers.

Properties
----------

*The `RTCRtpStreamStats` dictionary is based on [`RTCStats`](rtcstats), and inherits its properties. In addition, some or all of the following properties are available.*

### Standard fields included for all media types

[`codecId`](rtcrtpstreamstats/codecid)  
A [`DOMString`](domstring) which uniquely identifies the object which was inspected to produce the <span class="page-not-created">`RTCCodecStats`</span> object associated with this [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) stream.

[`kind`](rtcrtpstreamstats/kind)  
A [`DOMString`](domstring) whose value is `"audio"` if the associated [`MediaStreamTrack`](mediastreamtrack) is audio-only or `"video"` if the track contains video. This value will match that of the media type indicated by <span class="page-not-created">`RTCCodecStats.codec`</span>, as well as the track's [`kind`](mediastreamtrack/kind) property. Previously called `mediaType`.

[`ssrc`](rtcrtpstreamstats/ssrc)  
The 32-bit integer which identifies the source of the RTP packets this `RTCRtpStreamStats` object covers. This value is generated per the [RFC 3550](https://tools.ietf.org/html/rfc3550) specification.

[`trackId`](rtcrtpstreamstats/trackid)  
A [`DOMString`](domstring) which uniquely identifies the <span class="page-not-created">`RTCMediaStreamTrackStats`</span> object representing the associated [`MediaStreamTrack`](mediastreamtrack). This is *not* the same as the value of [`MediaStreamTrack.id`](mediastreamtrack/id).

[`transportId`](rtcrtpstreamstats/transportid)  
A [`DOMString`](domstring) uniquely identifying the object which was inspected to produce the <span class="page-not-created">`RTCTransportStats`</span> object associated with this RTP stream.

#### Obsolete fields

[`mediaType`](rtcrtpstreamstats/kind)  
Renamed to [`kind`](rtcrtpstreamstats/kind) in the specification in February 2018. See [Browser compatibility](rtcrtpstreamstats/kind#browser_compatibility) in [`RTCRtpStreamStats.kind`](rtcrtpstreamstats/kind) to determine when browsers made the transition.

### Local-only measurements

These properties are computed locally, and are only available to the device receiving the media stream. Their primary purpose is to examine the error resiliency of the connection, as they provide information about lost packets, lost frames, and how heavily compressed the data is.

[`firCount`](rtcrtpstreamstats/fircount)  
A count of the total number of Full Intra Request (FIR) packets received by the sender. This statistic is only available to the device which is receiving the stream and is only available for video tracks. A FIR packet is sent by the receiving end of the stream when it falls behind or has lost packets and is unable to continue decoding the stream; the sending end of the stream receives the FIR packet and responds by sending a full frame instead of a delta frame, thereby letting the receiver "catch up." The higher this number is, the more often a problem of this nature arose, which can be a sign of network congestion or an overburdened receiving device.

[`nackCount`](rtcrtpstreamstats/nackcount)  
The number of times the receiver notified the sender that one or more RTP packets has been lost by sending a Negative ACKnowledgement (NACK, also called "Generic NACK") packet to the sender. This value is only available to the receiver.

[`pliCount`](rtcrtpstreamstats/plicount)  
The number of times the receiving end of the stream sent a Picture Loss Indiciation (PLI) packet to the sender, indicating that it has lost some amount of encoded video data for one or more frames. Only the receiver has this value, and it's only valid for video tracks.

[`qpSum`](rtcrtpstreamstats/qpsum)  
The sum of the Quantization Parameter (QP) values associated with every frame received to date on the video track described by this `RTCRtpStreamStats` object. In general, the higher this number is, the more heavily compressed the video track was. Combined with <span class="page-not-created">`RTCReceivedRtpStreamStats.framesDecoded`</span> or <span class="page-not-created">`RTCSentRtpStreamStats.framesEncoded`</span>, you can approximate the average QP over those frames, keeping in mind that codecs often vary the quantizer values even within frames. Also keep in mind that the values of QP can vary from codec to codec, so this value is only potentially useful when compared against the same codec.

[`sliCount`](rtcrtpstreamstats/slicount)  
The number of times the receiver notified the sender that one or more consecutive (in scan order) encoded video macroblocks have been lost or corrupted; this notification is sent by the receiver to the sender using a Slice Loss Indication (SLI) packet. This is a fairly technical part of how codecs work and while the higher this value is, the more errors occurred in the stream, generally most of the time this value is only interesting to very intensively hardcore media developers.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#streamstats-dict*">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCRtpStreamStats' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCRtpStreamStats`

No

No

63

27

No

No

?

No

No

63

27

No

?

No

`codecId`

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

`firCount`

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

`isRemote`

No

No

27

In Firefox 28, a default value of `false` was added for `isRemote`, to match a specification update.

No

No

?

No

No

27

In Firefox 28, a default value of `false` was added for `isRemote`, to match a specification update.

No

?

No

`kind`

No

No

63

No

No

?

No

No

63

No

?

No

`mediaTrackId`

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

`mediaType`

No

No

34

No

No

?

No

No

34

No

?

No

`nackCount`

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

`qpSum`

No

No

66

No

No

?

No

No

66

No

?

No

`remoteId`

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

`transportId`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats</a>
