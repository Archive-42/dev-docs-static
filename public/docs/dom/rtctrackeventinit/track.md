RTCTrackEventInit.track
=======================

The [`RTCTrackEventInit`](../rtctrackeventinit) dictionary's `track` property specifies the [`MediaStreamTrack`](../mediastreamtrack) associated with the `track` event.

Syntax
------

    var trackEventInit = {
      receiver: rtpReceiver,
      track: mediaStreamTrack,
      streams: [videoStream],
      transceiver: rtpTransceiver
    };

    var track = trackEventInit.track;

### Value

A [`MediaStreamTrack`](../mediastreamtrack) representing the track with which the event is associated. This is the track that's being added to the [`RTCPeerConnection`](../rtcpeerconnection).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtctrackeventinit-track">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCTrackEventInit.track' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEventInit/track" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEventInit/track</a>
