MediaStreamTrack.kind
=====================

The `MediaStreamTrack.kind` read-only property returns a [`DOMString`](../domstring) set to `"audio"` if the track is an audio track and to `"video"`, if it is a video track. It doesn't change if the track is deassociated from its source.

Syntax
------

    const type = track.kind

### Value

The possible values are a [`DOMString`](../domstring) with on of the following values:

-   `"audio"`: the track is an audio track.
-   `"video"`: the track is a video track.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamtrack-kind">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStreamTrack.kind' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`kind`

Yes

12

Yes

No

Yes

11

Yes

Yes

Yes

Yes

11

Yes

See also
--------

-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/kind" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/kind</a>
