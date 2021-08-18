RTCRtpReceiver
==============

The `RTCRtpReceiver` interface of the [WebRTC API](webrtc_api) manages the reception and decoding of data for a [`MediaStreamTrack`](mediastreamtrack) on an [`RTCPeerConnection`](rtcpeerconnection).

Properties
----------

 [`RTCRtpReceiver.track`](rtcrtpreceiver/track) <span class="badge inline readonly">Read only </span>   
Returns the [`MediaStreamTrack`](mediastreamtrack) associated with the current `RTCRtpReceiver` instance.

 [`RTCRtpReceiver.transport`](rtcrtpreceiver/transport) <span class="badge inline readonly">Read only </span>   
Returns the [`RTCDtlsTransport`](rtcdtlstransport) instance over which the media for the receiver's track is received.

### Obsolete properties

 `rtcpTransport` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This property has been removed; the RTP and RTCP transports have been combined into a single transport. Use the [`transport`](rtcrtpreceiver/transport) property instead.

Methods
-------

[`RTCRtpReceiver.getContributingSources()`](rtcrtpreceiver/getcontributingsources)  
Returns an array of [`RTCRtpContributingSource`](rtcrtpcontributingsource) instances for each unique CSRC (contributing source) identifier received by the current `RTCRtpReceiver` in the last ten seconds.

 [`RTCRtpReceiver.getParameters()`](rtcrtpreceiver/getparameters)   
Returns an `RTCRtpParameters` object which contains information about how the RTC data is to be decoded.

[`RTCRtpReceiver.getStats()`](rtcrtpreceiver/getstats)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) whose fulfillment handler receives a [`RTCStatsReport`](rtcstatsreport) which contains statistics about the incoming streams and their dependencies.

 [`RTCRtpReceiver.getSynchronizationSources()`](rtcrtpreceiver/getsynchronizationsources)   
Returns an array including one [`RTCRtpSynchronizationSource`](rtcrtpsynchronizationsource) instance for each unique SSRC (synchronization source) identifier received by the current `RTCRtpReceiver` in the last ten seconds.

Static methods
--------------

[`RTCRtpReceiver.getCapabilities()`](rtcrtpreceiver/getcapabilities)  
Returns the most optimistic view of the capabilities of the system for receiving media of the given kind.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcrtpreceiver-interface">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpReceiver' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCRtpReceiver`

59

12

Yes

No

46

11

59

59

Yes

43

11

7.0

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

`getCapabilities`

59

12

Yes

No

46

12.1

59

59

Yes

43

12.2

7.0

`getContributingSources`

59

12

59

No

46

12.1

59

59

59

43

12.2

7.0

`getParameters`

59

≤79

Yes

No

46

11

59

59

Yes

43

11

7.0

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

7.0

`getSynchronizationSources`

73

≤79

59

No

60

12.1

73

73

59

52

12.2

11.0

`rtcpTransport`

59

12

Yes

No

46

No

59

59

Yes

43

No

7.0

`track`

59

12

Yes

No

46

11

59

59

Yes

43

11

7.0

`transport`

59

12

Yes

No

46

No

59

59

Yes

43

No

7.0

See also
--------

-   [WebRTC](webrtc_api)
-   [`RTCStatsReport`](rtcstatsreport)
-   [`RTCRtpSender`](rtcrtpsender)
-   [`RTCPeerConnection.getStats()`](rtcpeerconnection/getstats)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver</a>
