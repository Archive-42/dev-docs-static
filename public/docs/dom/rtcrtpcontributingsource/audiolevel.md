RTCRtpContributingSource.audioLevel
===================================

The read-only `audioLevel` property of the [`RTCRtpContributingSource`](../rtcrtpcontributingsource) interface indicates the audio level contained in the last RTP packet played from the described source. audioLevel will be the level value defined in \[RFC6465\] if the RFC 6465 header extension is present, and otherwise null.

Syntax
------

    var audioLevel = RTCRtpContributingSource.audioLevel

### Value

A double-precision floating-point number which indicates the volume level of the audio in the most recently received RTP packet from the source described by the `RTCRtpContributingSource`.

This value, which is in the range 0.0 to 1.0, is on a linear scale and its value is defined in dBov, or decibels (overload). This is the amplitude relative to the point at which clipping of the audio begins to occur. A value of 1.0 represents 0 dBov (maximum volume), a value of 0.0 represents silence, and a value of 0.5 represents approximately 6 dB SPL (decibels of sound pressure level) change in the sound pressure level from 0 dBov.

For both `RTCRtpContributingSource` and [`RTCRtpSynchronizationSource`](../rtcrtpsynchronizationsource), the audio level is converted to this form from the values defined in the specifications corresponding to each type of source.

`audioLevel` may be absent from `RTCRtpContributingSource` objects, which indicates that no volume level was provided by the source; however, it is *required* and always available on all `RTCRtpSynchronizationSource` objects.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpcontributingsource-audiolevel">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'audioLevel' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`audioLevel`

No

No

59

No

No

?

No

No

59

No

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpContributingSource/audioLevel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpContributingSource/audioLevel</a>
