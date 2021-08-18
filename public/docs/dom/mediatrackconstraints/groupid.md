MediaTrackConstraints.groupId
=============================

The [`MediaTrackConstraints`](../mediatrackconstraints) dictionary's `groupId` property is a [`ConstrainDOMString`](../constraindomstring) describing the requested or mandatory constraints placed upon the value of the [`groupId`](../mediatracksettings/groupid) constrainable property.

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.groupId`](../mediatracksupportedconstraints/groupid) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

Syntax
------

    var constraintsObject = { groupId: constraint };

    constraintsObject.groupId = constraint;

### Value

An object based on [`ConstrainDOMString`](../constraindomstring) specifying one or more acceptable, ideal, and/or exact (mandatory) group IDs which are acceptable as the source of media content.

Group IDs are unique for a given origin for the duration of a single browsing session, and are shared by all media sources that come from the same physical device. For example, the microphone and speaker on the same headset would share a group ID. This makes it possible to use the group ID to ensure that the audio and input devices are on the same headset by retrieving the group ID of the input device and specifying it when asking for an output device, perhaps.

However, the value of the `groupId` is determined by the source of the track's content, and there's no particular format mandated by the specification (although some kind of GUID is recommended). That means that a given track will only return one value for the `groupId` when you call [`getCapabilities()`](../mediastreamtrack/getcapabilities), and keep in mind that this value will change for each browsing session.

Because of this, there's no use for the group ID when calling [`MediaStreamTrack.applyConstraints()`](../mediastreamtrack/applyconstraints), since there is only one possible value, and you can't use it to ensure the same group is used across multiple browsing sessions when calling `getUserMedia()`.

Example
-------

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatrackconstraintset-groupid">Media Capture and Streams<br />
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

59

≤79

70

No

Yes

?

59

59

No

?

?

7.0

See also
--------

-   [Media Capture and Streams API](../media_streams_api)
-   [Capabilities, constraints, and settings](../media_streams_api/constraints)
-   [`MediaTrackConstraints`](../mediatrackconstraints)
-   [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints)
-   [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints)
-   [`MediaStreamTrack`](../mediastreamtrack)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/groupId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/groupId</a>
