# MediaTrackSettings.autoGainControl

The [`MediaTrackSettings`](../mediatracksettings) dictionary's `autoGainControl` property is a Boolean value whose value indicates whether or not automatic gain control (AGC) is enabled on an audio track. This lets you determine what value was selected to comply with your specified constraints for this property's value as described in the [`MediaTrackConstraints.autoGainControl`](../mediatrackconstraints/autogaincontrol) property you provided when calling either [`getUserMedia()`](../mediadevices/getusermedia) or [`MediaStreamTrack.applyConstraints()`](../mediastreamtrack/applyconstraints).

Automatic gain control is a feature in which a sound source automatically manages changes in the volume of its source media to maintain a steady overall volume level. This feature is typically used on microphones, although it can be provided by other input sources as well.

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.autoGainControl`](../mediatracksupportedconstraints/autogaincontrol) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

## Syntax

    var autoGainControl = MediaTrackSettings.autoGainControl;

### Value

A Boolean value which is `true` if the track has automatic gain control enabled or `false` if AGC is disabled.

## Example

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatracksettings-autogaincontrol">Media Capture and Streams<br />
<span class="small">The definition of 'autoGainControl' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`autoGainControl`

Yes

≤79

55

50-55

No

Yes

?

Yes

Yes

55

50-55

Yes

?

Yes

## See also

- [Media Capture and Streams API](../media_streams_api)
- [Capabilities, constraints, and settings](../media_streams_api/constraints)
- [`MediaTrackConstraints.autoGainControl`](../mediatrackconstraints/autogaincontrol)
- [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/autoGainControl" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/autoGainControl</a>
