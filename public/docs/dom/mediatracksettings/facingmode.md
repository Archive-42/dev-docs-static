# MediaTrackSettings.facingMode

The [`MediaTrackSettings`](../mediatracksettings) dictionary's `facingMode` property is a [`DOMString`](../domstring) indicating the direction in which the camera producing the video track represented by the [`MediaStreamTrack`](../mediastreamtrack) is currently facing. This lets you determine what value was selected to comply with your specified constraints for this property's value as described in the [`MediaTrackConstraints.facingMode`](../mediatrackconstraints/facingmode) property you provided when calling either [`getUserMedia()`](../mediadevices/getusermedia) or [`MediaStreamTrack.applyConstraints()`](../mediastreamtrack/applyconstraints).

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.facingMode`](../mediatracksupportedconstraints/facingmode) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

Because [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) doesn't include this information, tracks associated with a [WebRTC](../webrtc_api) [`RTCPeerConnection`](../rtcpeerconnection) will never include this property.

## Syntax

    var facingMode = MediaTrackSettings.facingMode;

### Value

A [`DOMString`](../domstring) whose value is one of the strings in `VideoFacingModeEnum`.

### VideoFacingModeEnum

The following strings are permitted values for the facing mode. These may represent separate cameras, or they may represent directions in which an adjustable camera can be pointed.

`"user"`  
The video source is facing toward the user; this includes, for example, the front-facing camera on a smartphone.

`"environment"`  
The video source is facing away from the user, thereby viewing their environment. This is the back camera on a smartphone.

`"left"`  
The video source is facing toward the user but to their left, such as a camera aimed toward the user but over their left shoulder.

`"right"`  
The video source is facing toward the user but to their right, such as a camera aimed toward the user but over their right shoulder.

## Example

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatracksettings-facingmode">Media Capture and Streams<br />
<span class="small">The definition of 'facingMode' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`facingMode`

Yes

≤79

69

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
- [`MediaTrackConstraints.facingMode`](../mediatrackconstraints/facingmode)
- [`MediaTrackSettings`](../mediatracksettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/facingMode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/facingMode</a>
