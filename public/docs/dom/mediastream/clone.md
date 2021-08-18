# MediaStream.clone()

The `clone()` method of the [`MediaStream`](../mediastream) interface creates a duplicate of the `MediaStream`. This new `MediaStream` object has a new unique [`id`](id) and contains clones of every [`MediaStreamTrack`](../mediastreamtrack) contained by the `MediaStream` on which `clone()` was called.

## Syntax

    var stream = MediaStream.clone();

### Parameters

None.

### Return value

A new [`MediaStream`](../mediastream) instance which has a new unique ID and contains clones of every [`MediaStreamTrack`](../mediastreamtrack) contained by the `MediaStream` on which `clone()` was called.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastream-clone">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStream.clone()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

No

11

45

45

48

No

11

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/clone" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/clone</a>
