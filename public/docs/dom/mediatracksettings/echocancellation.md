MediaTrackSettings.echoCancellation
===================================

The [`MediaTrackSettings`](../mediatracksettings) dictionary's `echoCancellation` property is a Boolean value whose value indicates whether or not echo cancellation is enabled on an audio track. This lets you determine what value was selected to comply with your specified constraints for this property's value as described in the [`MediaTrackConstraints.echoCancellation`](../mediatrackconstraints/echocancellation) property you provided when calling either [`getUserMedia()`](../mediadevices/getusermedia) or [`MediaStreamTrack.applyConstraints()`](../mediastreamtrack/applyconstraints).

Echo cancellation is a feature which attempts to prevent echo effects on a two-way audio connection by attempting to reduce or eliminate crosstalk between the user's output device and their input device. For example, it might apply a filter that negates the sound being produced on the speakers from being included in the input track generated from the microphone.

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.echoCancellation`](../mediatracksupportedconstraints/echocancellation) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

Because [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) doesn't include this information, tracks associated with a [WebRTC](../webrtc_api) [`RTCPeerConnection`](../rtcpeerconnection) will never include this property.

Syntax
------

    var echoCancellation = MediaTrackSettings.echoCancellation;

### Value

A Boolean value which is `true` if the track has echo cancellation functionality enabled or `false` if echo cancellation is disabled.

Example
-------

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatracksettings-echocancellation">Media Capture and Streams<br />
<span class="small">The definition of 'echoCancellation' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

Browser compatibility
---------------------

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

Yes

≤79

50

No

Yes

?

Yes

Yes

50

Yes

?

Yes

See also
--------

-   [Media Capture and Streams API](../media_streams_api)
-   [Capabilities, constraints, and settings](../media_streams_api/constraints)
-   [`MediaTrackConstraints.echoCancellation`](../mediatrackconstraints/echocancellation)
-   [`MediaTrackSettings`](../mediatracksettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/echoCancellation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/echoCancellation</a>
