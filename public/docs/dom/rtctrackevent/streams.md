RTCTrackEvent.streams
=====================

The [WebRTC API](../webrtc_api) interface [`RTCTrackEvent`](../rtctrackevent)'s read-only `streams` property specifies an array of [`MediaStream`](../mediastream) objects, one for each of the streams that comprise the track being added to the [`RTCPeerConnection`](../rtcpeerconnection).

Syntax
------

    var streams = trackEvent.streams;

### Value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`MediaStream`](../mediastream) objects, one for each stream that make up the new track.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtctrackevent-streams">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCTrackEvent.streams' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

11

56

56

44

43

11

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/streams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/streams</a>
