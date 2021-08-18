RTCRtpTransceiver
=================

The WebRTC interface `RTCRtpTransceiver` describes a permanent pairing of an [`RTCRtpSender`](rtcrtpsender) and an [`RTCRtpReceiver`](rtcrtpreceiver), along with some shared state.

Each [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) media section describes one bidirectional SRTP ("Secure Real Time Protocol") stream (excepting the media section for [`RTCDataChannel`](rtcdatachannel), if present). This pairing of send and receive SRTP streams is significant for some applications, so `RTCRtpTransceiver` is used to represent this pairing, along with other important state from the media section. Each non-disabled SRTP media section is always represented by exactly one transceiver.

A transceiver is uniquely identified using its [`mid`](rtcrtptransceiver/mid) property, which is the same as the media ID (`mid`) of its corresponding m-line. An `RTCRtpTransceiver` is **associated** with an m-line if its `mid` is non-null; otherwise it's considered disassociated.

Properties
----------

 [`currentDirection`](rtcrtptransceiver/currentdirection) <span class="badge inline readonly">Read only </span>   
A read-only string from the enum [`RTCRtpTransceiverDirection`](rtcrtptransceiverdirection) which indicates the transceiver's current directionality, or `null` if the transceiver is stopped or has never participated in an exchange of offers and answers. To change the transceiver's directionality, set the value of the [`direction`](rtcrtptransceiver/direction) property.

[`direction`](rtcrtptransceiver/direction)  
A string from the enum [`RTCRtpTransceiverDirection`](rtcrtptransceiverdirection) which is used to set the transceiver's desired direction.

 [`mid`](rtcrtptransceiver/mid) <span class="badge inline readonly">Read only </span>   
The media ID of the m-line associated with this transceiver. This association is established, when possible, whenever either a local or remote description is applied. This field is `null` if neither a local or remote description has been applied, or if its associated m-line is rejected by either a remote offer or any answer.

 [`receiver`](rtcrtptransceiver/receiver) <span class="badge inline readonly">Read only </span>   
The [`RTCRtpReceiver`](rtcrtpreceiver) object that handles receiving and decoding incoming media.

 [`sender`](rtcrtptransceiver/sender) <span class="badge inline readonly">Read only </span>   
The [`RTCRtpSender`](rtcrtpsender) object responsible for encoding and sending data to the remote peer.

[`stopped`](rtcrtptransceiver/stopped)  
Indicates whether or not sending and receiving using the paired `RTCRtpSender` and `RTCRtpReceiver` has been permanently disabled, either due to SDP offer/answer, or due to a call to [`stop()`](rtcrtptransceiver/stop).

Methods
-------

[`setCodecPreferences()`](rtcrtptransceiver/setcodecpreferences)  
A list of [`RTCRtpCodecParameters`](rtcrtpcodecparameters) objects which override the default preferences used by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) for the transceiver's codecs.

[`stop()`](rtcrtptransceiver/stop)  
Permanently stops the `RTCRtpTransceiver`. The associated sender stops sending data, and the associated receiver likewise stops receiving and decoding incoming data.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcrtptransceiver-interface">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpTransceiver' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`RTCRtpTransceiver`

69

≤18

59

No

No

11

69

69

59

No

11

10.0

`currentDirection`

69

No

59

No

No

12.1

69

69

59

No

12.2

10.0

`direction`

69

No

59

No

No

11

69

69

59

No

11

10.0

`mid`

69

No

59

No

No

11

69

69

59

No

11

10.0

`receiver`

69

No

59

No

No

11

69

69

59

No

11

10.0

`sender`

69

No

59

No

No

11

69

69

59

No

11

10.0

`setCodecPreferences`

No

No

No

No

No

13.1

No

No

No

No

13.4

No

`stop`

88

88

59

No

No

11

88

88

59

No

11

No

`stopped`

69

No

59

No

No

11

69

69

59

No

11

10.0

See also
--------

-   [WebRTC API](webrtc_api)
-   [Introduction to the Real-time Transport Protocol (RTP)](webrtc_api/intro_to_rtp)
-   [`RTCPeerConnection.addTrack()`](rtcpeerconnection/addtrack) and [`RTCPeerConnection.addTransceiver()`](rtcpeerconnection/addtransceiver) both create transceivers
-   [`RTCRtpReceiver`](rtcrtpreceiver) and [`RTCRtpSender`](rtcrtpsender)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver</a>
