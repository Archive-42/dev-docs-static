MediaTrackConstraints.logicalSurface
====================================

The [`MediaTrackConstraints`](../mediatrackconstraints) dictionary's `logicalSurface` property is a [`ConstrainDOMString`](../constraindomstring) describing the requested or mandatory constraints placed upon the value of the [`logicalSurface`](../mediatracksettings/logicalsurface) constrainable property. This is used to specify whether or not [`getDisplayMedia()`](../mediadevices/getdisplaymedia) should allow the user to choose display surfaces which are not necessarily fully visible on the screen, such as occluded windows or the complete content of windows which are large enough to require scrolling to see their entire contents.

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.logicalSurface`](../mediatracksupportedconstraints/logicalsurface) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

Syntax
------

    var constraintsObject = { logicalSurface: constraint };

    constraintsObject.logicalSurface = constraint;

### Value

A [`ConstrainBoolean`](../constrainboolean) which is `true` if logical surfaces should be permitted among the selections available to the user.

See [How constraints are defined](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an explanation of how to define constraints.

Usage notes
-----------

You can check the setting selected by the user agent after the display media has been created by [`getDisplayMedia()`](../mediadevices/getdisplaymedia) by calling [`getSettings()`](../mediastreamtrack/getsettings) on the display media's video [`MediaStreamTrack`](../mediastreamtrack), then checking the value of the returned [`MediaTrackSettings`](../mediatracksettings) object's [`logicalSurface`](../mediatracksettings/logicalsurface) object.

For example, if your app needs to know if the selected display surface is a logical one:

    let isLogicalSurface = displayStream.getVideoTracks()[0].getSettings().logicalSurface;

Following this code, `isLogicalSurface` is `true` if the display surface contained in the stream is a logical surface; that is, one which may not be entirely onscreen, or may even be entirely offscreen.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-screen-share/#dom-mediatrackconstraintset-logicalsurface">Screen Capture<br />
<span class="small">The definition of 'MediaTrackConstraints.logicalSurface' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`logicalSurface`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/logicalSurface" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/logicalSurface</a>
