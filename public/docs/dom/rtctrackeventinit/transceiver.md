RTCTrackEventInit.transceiver
=============================

The [`RTCTrackEventInit`](../rtctrackeventinit) dictionary's `transceiver` property specifies the [`RTCRtpTransceiver`](../rtcrtptransceiver) associated with the `track` event. The transceiver pairs the track's [`receiver`](../rtctrackevent/receiver) with an [`RTCRtpSender`](../rtcrtpsender) to allow bidirectional communication.

Syntax
------

    var trackEventInit = {
      receiver: rtpReceiver,
      track: mediaStreamTrack,
      streams: [videoStream],
      transceiver: rtpTransceiver
    };

    var rtpTransceiver = trackEventInit.transceiver;

### Value

The [`RTCRtpTransceiver`](../rtcrtptransceiver) which pairs the `receiver` with a sender and other properties which establish a single bidirectional [SRTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) stream for use by the [`track`](../rtctrackevent/track) associated with the `RTCTrackEvent`.

**Note:** The [`RTCRtpReceiver`](../rtcrtpreceiver) referred to by this `RTCRtpReceiver`'s [`receiver`](../rtcrtptransceiver/receiver) property will always be the same as the [`RTCTrackEvent`](../rtctrackevent)'s [`receiver`](../rtctrackevent/receiver) property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtctrackeventinit-transceiver">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCTrackEventInit.transceiver' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`transceiver`

69

≤18

59

No

43

?

69

69

59

43

?

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEventInit/transceiver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEventInit/transceiver</a>
