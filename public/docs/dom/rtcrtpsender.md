RTCRtpSender
============

The `RTCRtpSender` interface provides the ability to control and obtain details about how a particular [`MediaStreamTrack`](mediastreamtrack) is encoded and sent to a remote peer. With it, you can configure the encoding used for the corresponding track, get information about the device's media capabilities, and so forth. You can also obtain access to an [`RTCDTMFSender`](rtcdtmfsender) which can be used to send [DTMF](https://developer.mozilla.org/en-US/docs/Glossary/DTMF) codes (to simulate the user pressing buttons on a telephone's dial pad) to the remote peer.

Properties
----------

 [`RTCRtpSender.dtmf`](rtcrtpsender/dtmf) <span class="badge inline readonly">Read only </span>   
An [`RTCDTMFSender`](rtcdtmfsender) which can be used to send [DTMF](https://developer.mozilla.org/en-US/docs/Glossary/DTMF) tones using `telephone-event` payloads on the [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) session represented by the `RTCRtpSender` object. If `null`, the track and/or the connection doesn't support DTMF. Only audio tracks can support DTMF.

 [`RTCRtpSender.track`](rtcrtpsender/track) <span class="badge inline readonly">Read only </span>   
The [`MediaStreamTrack`](mediastreamtrack) which is being handled by the `RTCRtpSender`. If `track` is `null`, the `RTCRtpSender` doesn't transmit anything.

 [`RTCRtpSender.transport`](rtcrtpsender/transport) <span class="badge inline readonly">Read only </span>   
The [`RTCDtlsTransport`](rtcdtlstransport) over which the sender is exchanging the RTP and RTCP packets used to manage transmission of media and control data. This value is `null` until the transport is established. When bundling is in use, more than transceiver may be sharing the same transport object.

### Obsolete properties

 `rtcpTransport` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This property has been removed; the RTP and RTCP transports have been combined into a single transport. Use the [`transport`](rtcrtpsender/transport) property instead.

Methods
-------

[`RTCRtpSender.getParameters()`](rtcrtpsender/getparameters)  
Returns a [`RTCRtpParameters`](rtcrtpparameters) object describing the current configuration for the encoding and transmission of media on the `track`.

[`RTCRtpSender.getStats()`](rtcrtpsender/getstats)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled with a [`RTCStatsReport`](rtcstatsreport) which provides statistics data for all outbound streams being sent using this `RTCRtpSender`.

[`RTCRtpSender.setParameters()`](rtcrtpsender/setparameters)  
Applies changes to parameters which configure how the `track` is encoded and transmitted to the remote peer.

[`RTCRtpSender.setStreams()`](rtcrtpsender/setstreams)  
Sets the [`MediaStream`](mediastream)(s) associated with the [`track`](rtcrtpsender/track) being transmitted by this sender.

[`RTCRtpSender.replaceTrack()`](rtcrtpsender/replacetrack)  
Attempts to replace the track currently being sent by the `RTCRtpSender` with another track, without performing renegotiation. This method can be used, for example, to toggle between the front- and rear-facing cameras on a device.

Static methods
--------------

[`RTCRtpSender.getCapabilities()`](rtcrtpsender/getcapabilities)  
Returns an [`RTCRtpCapabilities`](rtcrtpcapabilities) object describing the system's capabilities for sending a specified kind of media data.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcrtpsender-interface">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpSender' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`RTCRtpSender`

64

12

34

No

51

11

64

64

34

47

11

9.0

`createEncodedStreams`

86

86

No

No

72

No

86

86

No

61

No

14.0

`dtmf`

66

≤18

52

No

53

13.1

66

66

52

47

13.4

9.0

`getCapabilities`

69

12

?

No

56

12.1

69

69

?

48

12.2

10.0

`getParameters`

68

≤79

Yes

No

55

11

68

68

Yes

48

11

10.0

`getStats`

67

≤18

55

No

54

12.1

67

67

55

48

12.2

9.0

`replaceTrack`

65

≤18

Yes

No

52

11

65

65

Yes

47

11

9.0

`rtcpTransport`

75

12-79

34

No

62

No

75

75

34

54

No

11.0

`setParameters`

68

≤79

64

Changes to parameters that should update live now do so starting in Firefox 64.

46

No

55

12.1

68

68

64

Changes to parameters that should update live now do so starting in Firefox 64.

46

48

12.2

10.0

`setStreams`

76

79

No

No

63

14.1

79

76

No

54

14.5

12.0

`track`

64

12

34

No

51

11

64

64

34

47

11

9.0

`transport`

75

12-79

34

No

62

No

75

75

34

54

No

11.0

See also
--------

-   WebRTC API
-   [`RTCPeerConnection.addTrack()`](rtcpeerconnection/addtrack)
-   [`RTCPeerConnection.getSenders()`](rtcpeerconnection/getsenders)
-   [`RTCRtpReceiver`](rtcrtpreceiver)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender</a>
