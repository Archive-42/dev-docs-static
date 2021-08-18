MediaTrackSettings.deviceId
===========================

The [`MediaTrackSettings`](../mediatracksettings) dictionary's `deviceId` property is a [`DOMString`](../domstring) which uniquely identifies the source for the corresponding [`MediaStreamTrack`](../mediastreamtrack) for the origin corresponding to the browsing session. This lets you determine what value was selected to comply with your specified constraints for this property's value as described in the [`MediaTrackConstraints.deviceId`](../mediatrackconstraints/deviceid) property you provided when calling either [`getUserMedia()`](../mediadevices/getusermedia).

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.deviceId`](../mediatracksupportedconstraints/deviceid) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

Because [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) doesn't include this information, tracks associated with a [WebRTC](../webrtc_api) [`RTCPeerConnection`](../rtcpeerconnection) will never include this property.

Syntax
------

    var deviceId = MediaTrackSettings.deviceId;

### Value

A [`DOMString`](../domstring) whose value is an origin-unique identifier for the track's source. This ID is valid across multiple browsing sessions for the same origin and is guaranteed to be different for all other origins, so you can safely use it to request the same source be used for multiple sessions, for example.

The actual value of the string, however, is determined by the source of the track, and there is no guarantee what form it will take, although the specification does recommend it be a GUID.

Since there is a one-to-one pairing of ID with each source, all tracks with the same source will share the same ID for any given origin, so [`MediaStreamTrack.getCapabilities()`](../mediastreamtrack/getcapabilities) will always return exactly one value for `deviceId`. That makes the device ID not useful for any changes to constraints when calling [`MediaStreamTrack.applyConstraints()`](../mediastreamtrack/applyconstraints).

An exception to the rule that device IDs are the same across browsing sessions: private browsing mode will use a different ID, and will change it each browsing session.

Example
-------

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatracksettings-deviceid">Media Capture and Streams<br />
<span class="small">The definition of 'deviceId' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`deviceId`

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
-   [`MediaTrackSettings.groupId`](groupid)
-   [`MediaTrackConstraints.deviceId`](../mediatrackconstraints/deviceid)
-   [`MediaTrackSettings`](../mediatracksettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/deviceId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/deviceId</a>
