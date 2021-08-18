RTCRtpReceiver.getSynchronizationSources()
==========================================

The `getSynchronizationSources()` method of the [`RTCRtpReceiver`](../rtcrtpreceiver) interface returns an array of [`RTCRtpContributingSource`](../rtcrtpcontributingsource) instances, each corresponding to one SSRC (synchronization source) identifier received by the current `RTCRtpReceiver` in the last ten seconds.

Syntax
------

    var rtcRtpContributingSources = rtcRtpReceiver.getContributingSources()

### Parameters

None.

### Return value

An array of [`RTCRtpSynchronizationSource`](../rtcrtpsynchronizationsource) instances. Each instance describes one of the synchronization sources that provided data to the incoming stream in the past ten seconds.

As you'll see in the documentarion for `RTCRtpSynchronizationSource`, it inherits the properties of [`RTCRtpContributingSource`](../rtcrtpcontributingsource), including [`timestamp`](../rtcrtpcontributingsource/timestamp), [`source`](../rtcrtpcontributingsource/source), and [`audioLevel`](../rtcrtpcontributingsource/audiolevel).

The synchronization source objects add a [`voiceActivityFlag`](../rtcrtpsynchronizationsource/voiceactivityflag) property, which indicates if the last RTP packet received contained voice activity.

### Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpreceiver-getsynchronizationsources">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'getSynchronizationSources()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`audio_tracks_supported`

73

79

59

No

60

?

73

73

59

52

?

11.0

`video_tracks_supported`

73

≤79

68

No

60

?

73

73

68

52

?

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/getSynchronizationSources" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/getSynchronizationSources</a>
