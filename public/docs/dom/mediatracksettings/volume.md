MediaTrackSettings.volume
=========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [`MediaTrackSettings`](../mediatracksettings) dictionary's `volume` property is a double-precision floating-point number indicating the volume of the [`MediaStreamTrack`](../mediastreamtrack) as currently configured, as a value from 0.0 (silence) to 1.0 (maximum supported volume for the device). This lets you determine what value was selected to comply with your specified constraints for this property's value as described in the [`MediaTrackConstraints.volume`](../mediatrackconstraints/volume) property you provided when calling either [`getUserMedia()`](../mediadevices/getusermedia) or [`MediaStreamTrack.applyConstraints()`](../mediastreamtrack/applyconstraints).

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.volume`](../mediatracksupportedconstraints/volume) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

Syntax
------

    var volume = MediaTrackSettings.volume;

### Value

A double-precision floating-point number indicating the volume, from 0.0 to 1.0, of the audio track as currently configured.

Example
-------

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

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

`volume`

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
-   [`MediaTrackConstraints.volume`](../mediatrackconstraints/volume)
-   [`MediaTrackSettings`](../mediatracksettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/volume" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/volume</a>
