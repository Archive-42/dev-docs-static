RTCRtpReceiver.getContributingSources()
=======================================

The `getContributingSources()` method of the [`RTCRtpReceiver`](../rtcrtpreceiver) interface returns an array of [`RTCRtpContributingSource`](../rtcrtpcontributingsource) instances, each corresponding to one CSRC (contributing source) identifier received by the current `RTCRtpReceiver` in the last ten seconds.

Syntax
------

    var rtcRtpContributingSources = rtcRtpReceiver.getContributingSources()

### Parameters

None.

### Return value

An array of [`RTCRtpContributingSource`](../rtcrtpcontributingsource) instances. Each instance describes one of the contributing sources that provided data to the incoming stream in the past ten seconds.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpreceiver-getcontributingsources">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'getContributingSources()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`audio_tracks_supported`

59

12

59

No

46

?

59

59

59

43

?

7.0

`video_tracks_supported`

73

≤79

68

No

?

?

73

73

68

?

?

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/getContributingSources" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/getContributingSources</a>
