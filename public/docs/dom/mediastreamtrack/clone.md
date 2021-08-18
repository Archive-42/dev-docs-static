# MediaStreamTrack.clone()

The `clone()` method of the [`MediaStreamTrack`](../mediastreamtrack) interface creates a duplicate of the `MediaStreamTrack`. This new `MediaStreamTrack` object is identical except for its unique [`id`](id).

## Syntax

    const newTrack = track.clone()

### Return value

A new [`MediaStreamTrack`](../mediastreamtrack) instance which is identical to the one `clone()` was called, except for its new unique [`id`](id).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamtrack-clone">Media Capture and Streams<br />
<span class="small">The definition of 'clone()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`clone`

45

12

48

No

32

11

45

45

Yes

32

11

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/clone" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/clone</a>
