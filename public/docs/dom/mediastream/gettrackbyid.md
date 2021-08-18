# MediaStream.getTrackById()

The `MediaStream.getTrackById()` method returns a [`MediaStreamTrack`](../mediastreamtrack) object representing the track with the specified ID string. If there is no track with the specified ID, this method returns `null`.

## Syntax

    var track = MediaStream.getTrackById(id);

### Parameters

`id`  
A [`DOMString`](../domstring) which identifies the track to be returned.

### Return value

If a track is found for which [`MediaStreamTrack.id`](../mediastreamtrack/id) matches the specified `id` string, that [`MediaStreamTrack`](../mediastreamtrack) object is returned. Otherwise, the returned value is `null`.

## Example

This example activates a commentary track on a video by ducking the audio level of the main audio track to 50%, then enabling the commentary track.

    stream.getTrackById("primary-audio-track").applyConstraints({ volume: 0.5 });
    stream.getTrackById("commentary-track").enabled = true;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastream-gettrackbyid">Media Capture and Streams<br />
<span class="small">The definition of 'getTrackById()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`getTrackById`

26

12

49

No

No

11

37

26

49

No

11

1.5

## See also

- [`MediaStream`](../mediastream)
- [`MediaStreamTrack.id`](../mediastreamtrack/id)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/getTrackById" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/getTrackById</a>
