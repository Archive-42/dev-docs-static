MediaTrackSettings.channelCount
===============================

The [`MediaTrackSettings`](../mediatracksettings) dictionary's `channelCount` property is an integer indicating how many audio channel the [`MediaStreamTrack`](../mediastreamtrack) is currently configured to have. This lets you determine what value was selected to comply with your specified constraints for this property's value as described in the [`MediaTrackConstraints.channelCount`](../mediatrackconstraints/channelcount) property you provided when calling either [`getUserMedia()`](../mediadevices/getusermedia) or [`MediaStreamTrack.applyConstraints()`](../mediastreamtrack/applyconstraints).

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.channelCount`](../mediatracksupportedconstraints/channelcount) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

Syntax
------

    var channelCount = MediaTrackSettings.channelCount;

### Value

An integer value indicating the number of audio channels on the track. A value of 1 indicates monaural sound, 2 means stereo, and so forth.

Example
-------

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatracksettings-channelcount">Media Capture and Streams<br />
<span class="small">The definition of 'channelCount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`channelCount`

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

See also
--------

-   [Media Capture and Streams API](../media_streams_api)
-   [Capabilities, constraints, and settings](../media_streams_api/constraints)
-   [`MediaTrackConstraints.channelCount`](../mediatrackconstraints/channelcount)
-   [`MediaTrackSettings`](../mediatracksettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/channelCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/channelCount</a>
