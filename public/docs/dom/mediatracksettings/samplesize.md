# MediaTrackSettings.sampleSize

The [`MediaTrackSettings`](../mediatracksettings) dictionary's `sampleSize` property is an integer indicating the linear sample size (in bits per sample) the [`MediaStreamTrack`](../mediastreamtrack) is currently configured for. This lets you determine what value was selected to comply with your specified constraints for this property's value as described in the [`MediaTrackConstraints.sampleSize`](../mediatrackconstraints/samplesize) property you provided when calling either [`getUserMedia()`](../mediadevices/getusermedia) or [`MediaStreamTrack.applyConstraints()`](../mediastreamtrack/applyconstraints).

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.sampleSize`](../mediatracksupportedconstraints/samplesize) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

## Syntax

    var sampleSize = MediaTrackSettings.sampleSize;

### Value

An integer value indicating how many bits each audio sample is represented by. The most commonly used sample size for many years now is 16 bits per sample, which was used for CD audio among others. Other common sample sizes are 8 (for reduced bandwidth requirements) and 24 (for high-resolution professional audio).

Each audio channel on the track requires sampleSize bits. That means that a given sample actually uses (`sampleSize`/8)\*[`channelCount`](channelcount) bytes of data. For example, 16-bit stereo audio requires (16/8)\*2 or 4 bytes per sample.

## Example

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatracksettings-samplesize">Media Capture and Streams<br />
<span class="small">The definition of 'sampleSize' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`sampleSize`

Yes

≤79

No

No

Yes

?

Yes

Yes

No

Yes

?

Yes

## See also

- [Media Capture and Streams API](../media_streams_api)
- [Capabilities, constraints, and settings](../media_streams_api/constraints)
- [`MediaTrackConstraints.sampleSize`](../mediatrackconstraints/samplesize)
- [`MediaTrackSettings`](../mediatracksettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/sampleSize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/sampleSize</a>
