# MediaTrackSettings.latency

The [`MediaTrackSettings`](../mediatracksettings) dictionary's `latency` property is a double-precision floating-point number indicating the estimated latency (specified in seconds) of the [`MediaStreamTrack`](../mediastreamtrack) as currently configured. This lets you determine what value was selected to comply with your specified constraints for this property's value as described in the [`MediaTrackConstraints.latency`](../mediatrackconstraints/latency) property you provided when calling either [`getUserMedia()`](../mediadevices/getusermedia) or [`MediaStreamTrack.applyConstraints()`](../mediastreamtrack/applyconstraints).

This is, of course, an approximation, since latency can vary for many reasons including CPU, transmission, and storage overhead.

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.latency`](../mediatracksupportedconstraints/latency) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

Because [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) doesn't include this information, tracks associated with a [WebRTC](../webrtc_api) [`RTCPeerConnection`](../rtcpeerconnection) will never include this property.

## Syntax

    var latency = MediaTrackSettings.latency;

### Value

A double-precision floating-point number indicating the estimated latency, in seconds, of the audio track as currently configured.

## Example

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatracksettings-latency">Media Capture and Streams<br />
<span class="small">The definition of 'latency' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`latency`

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
- [`MediaTrackConstraints.latency`](../mediatrackconstraints/latency)
- [`MediaTrackSettings`](../mediatracksettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/latency" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/latency</a>
