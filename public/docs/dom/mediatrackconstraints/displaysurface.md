MediaTrackConstraints.displaySurface
====================================

The [`MediaTrackConstraints`](../mediatrackconstraints) dictionary's `displaySurface` property is a [`ConstrainDOMString`](../constraindomstring) describing the requested or mandatory constraints placed upon the value of the [`displaySurface`](../mediatracksettings/displaysurface) constrainable property. This is used to specify the type or types of display surfaces which [`getDisplayMedia()`](../mediadevices/getdisplaymedia) will let the user select among for sharing purposes.

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.displaySurface`](../mediatracksupportedconstraints/displaysurface) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

Syntax
------

    var constraintsObject = { displaySurface: constraint };

    constraintsObject.displaySurface = constraint;

### Value

A [`ConstrainDOMString`](../constraindomstring) which specifies the type of display surface that's being captured. This value *does not* affect the list of display sources in the browser's user interface.

See [How constraints are defined](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an explanation of how to define constraints.

Usage notes
-----------

You can check the setting selected by the user agent after the display media has been created by [`getDisplayMedia()`](../mediadevices/getdisplaymedia) by calling [`getSettings()`](../mediastreamtrack/getsettings) on the display media's video [`MediaStreamTrack`](../mediastreamtrack), then checking the value of the returned [`MediaTrackSettings`](../mediatracksettings) object's [`displaySurface`](../mediatracksettings/displaysurface) object.

For example, if your app needs to know that the surface being shared is a monitor or application—meaning that there's possibly a non-content backdrop—it can use code similar to this:

    let mayHaveBackdropFlag = false;
    let displaySurface = displayStream.getVideoTracks()[0].getSettings().displaySurface;

    if (displaySurface === "monitor" || displaySurface ==="application") {
      mayHaveBackdropFlag = true;
    }

Following this code, `mayHaveBackdrop` is `true` if the display surface contained in the stream is of type `monitor` or `application`; either of these *may* have non-content backdrop areas. Later code can use this flag to determine whether or not to perform special processing, such as to remove or replace the backdrop, or to "cut" the individual display areas out of the received frames of video.

Examples
--------

Here are some example constraints objects for `getDisplayMedia()` that make use of the `displaySurface` property. In addition, see [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for a complete example showing how constraints are used.

TBD

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-screen-share/#dom-mediatrackconstraintset-displaysurface">Screen Capture<br />
<span class="small">The definition of 'MediaTrackConstraints.displaySurface' in that specification.</span></a></td><td><span class="spec-">Unknown</span></td><td>Initial specification.</td></tr></tbody></table>

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

`displaySurface`

No

No

No

No

Yes

?

No

No

No

?

?

No

See also
--------

-   [Screen Capture API](../screen_capture_api)
-   [Using the Screen Capture API](../screen_capture_api/using_screen_capture)
-   [Capabilities, constraints, and settings](../media_streams_api/constraints)
-   [`MediaTrackConstraints`](../mediatrackconstraints)
-   [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints)
-   [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/displaySurface" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/displaySurface</a>
