RTCTrackEventInit.receiver
==========================

The [`RTCTrackEventInit`](../rtctrackeventinit) dictionary's `receiver` property specifies the [`RTCRtpReceiver`](../rtcrtpreceiver) associated with the event.

Syntax
------

    var trackEventInit = {
      receiver: rtpReceiver,
      track: mediaStreamTrack,
      streams: [videoStream],
      transceiver: rtpTransceiver
    };

    var rtpReceiver = trackEventInit.receiver;

### Value

The [`RTCRtpTransceiver`](../rtcrtptransceiver) which pairs the `receiver` with a sender and other properties which establish a single bidirectional [SRTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) stream for use by the [`track`](../rtctrackevent/track) associated with the `RTCTrackEvent`.

**Note:** The [`transceiver`](../rtctrackevent/transceiver) includes its own [`receiver`](../rtcrtptransceiver/receiver) property, which will always be the same [`RTCRtpReceiver`](../rtcrtpreceiver) as this one.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtctrackeventinit-receiver">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCTrackEventInit.receiver' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`receiver`

56

≤18

22

No

43

?

56

56

44

43

?

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEventInit/receiver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEventInit/receiver</a>
