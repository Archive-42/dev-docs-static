MediaTrackConstraints.cursor
============================

The [`MediaTrackConstraints`](../mediatrackconstraints) dictionary's `cursor` property is a [`ConstrainDOMString`](../constraindomstring) describing the requested or mandatory constraints placed upon the value of the [`cursor`](../mediatracksettings/cursor) constrainable property, which is used to specify whether or not the cursor should be included in the captured video.

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.cursor`](../mediatracksupportedconstraints/cursor) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

Syntax
------

    var constraintsObject = { cursor: constraint };

    constraintsObject.cursor = constraint;

### Value

A [`ConstrainDOMString`](../constraindomstring) which specifies whether or not the mouse cursor should be rendered into the video track in the [`MediaStream`](../mediastream) returned by the call to [`getDisplayMedia()`](../mediadevices/getdisplaymedia). See [How constraints are defined](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an explanation of how to define constraints.

Usage notes
-----------

You can check the setting selected by the user agent after the display media has been created by [`getDisplayMedia()`](../mediadevices/getdisplaymedia) by calling [`getSettings()`](../mediastreamtrack/getsettings) on the display media's video [`MediaStreamTrack`](../mediastreamtrack), then checking the value of the returned [`MediaTrackSettings`](../mediatracksettings) object's [`cursor`](../mediatracksettings/cursor) object.

For example, if your app needs to alter the stream by inserting a representation of the cursor position if the stream doesn't include the rendered cursor, you can determine the need to do so by using code like this:

    let insertFakeCursorFlag = false;

    if (displayStream.getVideoTracks()[0].getSettings().cursor === "never") {
      insertFakeCursorFlag = true;
    }

Following this code, `insertFakeCursorFlag` is `true` if there's no cursor rendered into the stream already. Later code can detect this flag's value and if it's `true`, can manually look at some metadata that might be provided and insert a fake representation of the cursor at the correct position.

Examples
--------

Here are some example constraints objects for `getDisplayMedia()` that make use of the `cursor` property. In addition, see [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for a complete example showing how constraints are used.

### Example: Cursor always visible

This example sets up the constraints to request that the cursor always be visible.

    let displayMediaOptions = {
      cursor: "always"
    };

### Example: Cursor visible during motion with fallback

In this example, the `cursor` property is configured to request that the cursor be visible when in motion, falling back to always being visible if the user agent doesn't support in-motion only cursor rendering.

    let displayMediaOptions = {
      cursor: ["motion", "always"]
    };

### Example: Require that the cursor not be visible

This constraints object explicitly requires that the cursor *not* be rendered into the video track.

    let displayMediaOptions = {
      cursor: {
        exact: "none"
      }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-screen-share/#dom-mediatrackconstraintset-cursor">Screen Capture<br />
<span class="small">The definition of 'MediaTrackConstraints.cursor' in that specification.</span></a></td><td><span class="spec-">Unknown</span></td><td>Initial specification.</td></tr></tbody></table>

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

`cursor`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/cursor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/cursor</a>
