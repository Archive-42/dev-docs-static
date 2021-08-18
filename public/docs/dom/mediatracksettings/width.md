# MediaTrackSettings.width

The [`MediaTrackSettings`](../mediatracksettings) dictionary's `width` property is an integer indicating the number of pixels wide [`MediaStreamTrack`](../mediastreamtrack) is currently configured to be. This lets you determine what value was selected to comply with your specified constraints for this property's value as described in the [`MediaTrackConstraints.width`](../mediatrackconstraints/width) property you provided when calling either [`getUserMedia()`](../mediadevices/getusermedia) or [`MediaStreamTrack.applyConstraints()`](../mediastreamtrack/applyconstraints).

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.width`](../mediatracksupportedconstraints/width) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

## Syntax

    var width = MediaTrackSettings.width;

### Value

An integer value indicating the width, in pixels, of the video track as currently configured.

## Example

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatracksettings-width">Media Capture and Streams<br />
<span class="small">The definition of 'width' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`width`

Yes

≤79

36

No

Yes

?

Yes

Yes

36

Yes

?

Yes

## See also

- [Media Capture and Streams API](../media_streams_api)
- [Capabilities, constraints, and settings](../media_streams_api/constraints)
- [`MediaTrackConstraints.width`](../mediatrackconstraints/width)
- [`MediaTrackSettings`](../mediatracksettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/width</a>
