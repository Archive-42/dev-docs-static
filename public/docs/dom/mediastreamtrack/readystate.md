MediaStreamTrack.readyState
===========================

The `MediaStreamTrack.readyState` read-only property returns an enumerated value giving the status of the track.

Syntax
------

    const state = track.readyState

### Value

It takes one of the following values:

-   `"live"` which indicates that an input is connected and does its best-effort in providing real-time data. In that case, the output of data can be switched on or off using the [`MediaStreamTrack.enabled`](enabled) property.
-   `"ended"` which indicates that the input is not giving any more data and will never provide new data.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamtrack-readystate">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStreamTrack.readyState' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`readyState`

Yes

12

50

No

Yes

11

Yes

Yes

50

Yes

11

Yes

See also
--------

-   [Media Stream API](../media_streams_api)
-   [WebRTC](../webrtc_api)
-   [`MediaStreamTrack.onended`](onended)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/readyState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/readyState</a>
