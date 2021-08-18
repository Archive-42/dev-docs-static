RTCRtpSender.track
==================

The `track` read-only property of the [`RTCRtpSender`](../rtcrtpsender) interface returns the [`MediaStreamTrack`](../mediastreamtrack) which is being handled by the `RTCRtpSender`.

Syntax
------

    var mediaStreamTrack = rtcRtpSender.track

### Value

A [`MediaStreamTrack`](../mediastreamtrack) object representing the media associated with the `RTCRtpSender`. If no track is associated with the sender, this value is `null`, in which case the sender transmits nothing.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpsender-track">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'track' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/track" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/track</a>
