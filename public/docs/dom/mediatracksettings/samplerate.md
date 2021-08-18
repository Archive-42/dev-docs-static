# MediaTrackSettings.sampleRate

The [`MediaTrackSettings`](../mediatracksettings) dictionary's `sampleRate` property is an integer indicating how many audio samples per second the [`MediaStreamTrack`](../mediastreamtrack) is currently configured for. This lets you determine what value was selected to comply with your specified constraints for this property's value as described in the [`MediaTrackConstraints.sampleRate`](../mediatrackconstraints/samplerate) property you provided when calling either [`getUserMedia()`](../mediadevices/getusermedia) or [`MediaStreamTrack.applyConstraints()`](../mediastreamtrack/applyconstraints).

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.sampleRate`](../mediatracksupportedconstraints/samplerate) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

## Syntax

    var sampleRate = MediaTrackSettings.sampleRate;

### Value

An integer value indicating how many samples each second of audio data includes. Common values include 44,100 (standard CD audio), 48,000 (standard digital audio), 96,000 (commonly used in audio mastering and post-production), and 192,000 (used for high-resolution audio in professional recording and mastering sessions). However, lower values are often used to reduce bandwidth requirements; 8,000 samples per second is adequate for comprehensible albeit imperfect human speech, and both 11,025 FPS and 22,050 FPS are often used for low-bandwidth, reduced quality sound and music.

## Example

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatracksettings-samplerate">Media Capture and Streams<br />
<span class="small">The definition of 'sampleRate' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`sampleRate`

No

No

No

No

No

?

No

No

No

No

?

No

## See also

- [Media Capture and Streams API](../media_streams_api)
- [Capabilities, constraints, and settings](../media_streams_api/constraints)
- [`MediaTrackConstraints.sampleRate`](../mediatrackconstraints/samplerate)
- [`MediaTrackSettings`](../mediatracksettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/sampleRate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/sampleRate</a>
