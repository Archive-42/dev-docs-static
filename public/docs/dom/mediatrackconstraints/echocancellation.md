# MediaTrackConstraints.echoCancellation

The [`MediaTrackConstraints`](../mediatrackconstraints) dictionary's `echoCancellation` property is a [`ConstrainBoolean`](../constrainboolean) describing the requested or mandatory constraints placed upon the value of the [`echoCancellation`](../mediatracksettings/echocancellation) constrainable property.

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.echoCancellation`](../mediatracksupportedconstraints/echocancellation) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

Because [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) doesn't include this information, tracks associated with a [WebRTC](../webrtc_api) [`RTCPeerConnection`](../rtcpeerconnection) will never include this property.

## Syntax

    var constraintsObject = { echoCancellation: constraint };

    constraintsObject.echoCancellation = constraint;

### Value

If this value is a simple `true` or `false`, the user agent will attempt to obtain media with echo cancellation enabled or disabled as specified, if possible, but will not fail if this can't be done. If, instead, the value is given as an object with an `exact` field, that field's Boolean value indicates a required setting for the echo cancellation feature; if it can't be met, then the request will result in an error.

## Example

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatrackconstraintset-echocancellation">Media Capture and Streams<br />
<span class="small">The definition of 'echoCancellation' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`echoCancellation`

59

≤79

50

No

Yes

?

59

59

50

?

?

7.0

## See also

- [Media Capture and Streams API](../media_streams_api)
- [Capabilities, constraints, and settings](../media_streams_api/constraints)
- [`MediaTrackConstraints`](../mediatrackconstraints)
- [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints)
- [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints)
- [`MediaStreamTrack`](../mediastreamtrack)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/echoCancellation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/echoCancellation</a>
