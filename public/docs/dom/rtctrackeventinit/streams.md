RTCTrackEventInit.streams
=========================

The [`RTCTrackEventInit`](../rtctrackeventinit) dictionary's optional `streams` property provides an array containing a [`MediaStream`](../mediastream) object for each of the streams associated with the event's track.

Syntax
------

    var trackEventInit = {
      receiver: rtpReceiver,
      track: mediaStreamTrack,
      streams: [videoStream],
      transceiver: rtpTransceiver
    };

    var streamList = trackEventInit.streams;

### Value

An array of [`MediaStream`](../mediastream) objects, one for each stream which make up the track.

If `streams` is not specified, its default value is an empty array.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtctrackeventinit-streams">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCTrackEventInit.streams' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`streams`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEventInit/streams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEventInit/streams</a>
