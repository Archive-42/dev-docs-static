# MediaStream.addTrack()

The `MediaStream.addTrack()` method adds a new track to the stream. The track is specified as a parameter of type [`MediaStreamTrack`](../mediastreamtrack).

If the specified track is already in the stream's track set, this method has no effect.

## Syntax

    stream.addTrack(track);

### Parameters

`track`  
A [`MediaStreamTrack`](../mediastreamtrack) to add to the stream.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

## Example

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastream-addtrack">Media Capture and Streams<br />
<span class="small">The definition of 'addTrack()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`addTrack`

26

12

44

No

No

11

37

26

No

No

11

1.5

## See also

- [`MediaStream`](../mediastream), the interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/addTrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/addTrack</a>
