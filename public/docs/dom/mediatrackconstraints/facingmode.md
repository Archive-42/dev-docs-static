# MediaTrackConstraints.facingMode

The [`MediaTrackConstraints`](../mediatrackconstraints) dictionary's `facingMode` property is a [`ConstrainDOMString`](../constraindomstring) describing the requested or mandatory constraints placed upon the value of the [`facingMode`](../mediatracksettings/facingmode) constrainable property.

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.facingMode`](../mediatracksupportedconstraints/facingmode) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

Because [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) doesn't include this information, tracks associated with a [WebRTC](../webrtc_api) [`RTCPeerConnection`](../rtcpeerconnection) will never include this property.

## Syntax

    var constraintsObject = { facingMode: constraint };

    constraintsObject.facingMode = constraint;

### Value

An object based on [`ConstrainDOMString`](../constraindomstring) specifying one or more acceptable, ideal, and/or exact (mandatory) facing modes are acceptable for a video track.

An `exact` value in this case indicates that the specified facing mode is specifically required; for example:

    var constraints = {
      facingMode: { exact: "user" }
    };

This indicates that only a user-facing camera is acceptable; if there is no user-facing camera, or the user declines permission to use that camera, the media request will fail.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatrackconstraintset-facingmode">Media Capture and Streams<br />
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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/facingMode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/facingMode</a>
