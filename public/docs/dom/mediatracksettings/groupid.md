MediaTrackSettings.groupId
==========================

The [`MediaTrackSettings`](../mediatracksettings) dictionary's `groupId` property is a browsing-session unique [`DOMString`](../domstring) which identifies the group of devices which includes the source for the [`MediaStreamTrack`](../mediastreamtrack). This lets you determine what value was selected to comply with your specified constraints for this property's value as described in the [`MediaTrackConstraints.groupId`](../mediatrackconstraints/groupid) property you provided when calling either [`getUserMedia()`](../mediadevices/getusermedia).

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.groupId`](../mediatracksupportedconstraints/groupid) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

Because [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) doesn't include this information, tracks associated with a [WebRTC](../webrtc_api) [`RTCPeerConnection`](../rtcpeerconnection) will never include this property.

Syntax
------

    var groupId = MediaTrackSettings.groupId;

### Value

A [`DOMString`](../domstring) whose value is a browsing-session unique identifier for a group of devices which includes the source of the track's contents. Two devices share the same group ID if they belong to the same physical hardware device. For example, a headset has two devices on it: a microphone which can serve as a source for audio tracks and a speaker which can serve as an output for audio.

The group ID is not usable across multiple browsing sessions. However, it can be used to ensure that audio input and output are both being performed on the same headset, for example, or to ensure that the built-in camera and microphone on a phone are being used for video conferencing purposes.

The actual value of the string, however, is determined by the source of the track, and there is no guarantee what form it will take, although the specification does recommend it be a GUID.

Since this property isn't stable across browsing sessions, its usefulness when calling [`getUserMedia()`](../mediadevices/getusermedia) is generally limited to ensuring that tasks performed during the same browsing session use devices from the same group (or that they don't use devices from the same group). There is no situation in which the groupId is useful when calling `applyConstraints()`, since the value can't be changed.

Example
-------

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatracksettings-groupid">Media Capture and Streams<br />
<span class="small">The definition of 'groupId' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`groupId`

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

See also
--------

-   [Media Capture and Streams API](../media_streams_api)
-   [Capabilities, constraints, and settings](../media_streams_api/constraints)
-   [`MediaTrackSettings.deviceId`](deviceid)
-   [`MediaTrackConstraints.groupId`](../mediatrackconstraints/groupid)
-   [`MediaTrackSettings`](../mediatracksettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/groupId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/groupId</a>
