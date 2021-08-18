MediaTrackSettings.aspectRatio
==============================

The [`MediaTrackSettings`](../mediatracksettings) dictionary's `aspectRatio` property is a double-precision floating-point number indicating the aspect ratio of the [`MediaStreamTrack`](../mediastreamtrack) as currently configured. This lets you determine what value was selected to comply with your specified constraints for this property's value as described in the [`MediaTrackConstraints.aspectRatio`](../mediatrackconstraints/aspectratio) property you provided when calling either [`getUserMedia()`](../mediadevices/getusermedia) or [`MediaStreamTrack.applyConstraints()`](../mediastreamtrack/applyconstraints).

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.aspectRatio`](../mediatracksupportedconstraints/aspectratio) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

Syntax
------

    var aspectRatio = MediaTrackSettings.aspectRatio;

### Value

A double-precision floating-point number indicating the current configuration of the track's aspect ratio. The aspect ratio is computed by taking the track's width, dividing by its height, and rounding the result to ten decimal places. For example, the standard 16:9 high-definition aspect ratio can be computed as 1920/1080, or 1.7777777778.

Example
-------

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatracksettings-aspectratio">Media Capture and Streams<br />
<span class="small">The definition of 'aspectRatio' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`aspectRatio`

Yes

≤79

No

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
-   [`MediaTrackConstraints.aspectRatio`](../mediatrackconstraints/aspectratio)
-   [`MediaTrackSettings`](../mediatracksettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/aspectRatio" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/aspectRatio</a>
