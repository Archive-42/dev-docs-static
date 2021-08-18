# MediaTrackSettings.logicalSurface

The [`MediaTrackSettings`](../mediatracksettings) dictionary's `logicalSurface` property indicates whether or not the display area being captured is a logical surface. Logical surfaces are those which are not necessarily entirely onscreen, or may even be off-screen, such as windows' backing buffers (where only part of the buffer is visible without scrolling the containing window) and offscreen rendering contexts.

## Syntax

    isLogicalSurface = mediaTrackSettings.logicalSurface;

### Value

A Boolean value which is `true` if the video track in the stream of captured video is taken from a logical display surface.

The most common scenario in which a display surface may be a logical one is if the selected surface contains the entire content area of a window which is too large to display onscreen at once. Since the window that contains the surface has to be scrolled to show the rest of the contents, the surface is a logical one.

A visible display surface (that is, a surface for which `logicalSurface` returns `false`) is the portion of a logical display surface which is currently visible onscreen.

For example, a user agent _may_ choose to allow the user to choose whether to share the entire document (a `browser` with `logicalSurface` value of `true`), or just the currently visible portion of the document (where the `logicalSurface` of the `browser` surface is `false`).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-screen-share/#dom-mediatrackconstraintset-logicalsurface">Screen Capture<br />
<span class="small">The definition of 'MediaTrackSettings.logicalSurface' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

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

71

≤79

No

No

Yes

?

71

71

No

?

?

10.0

## See also

- [Screen Capture API](../screen_capture_api)
- [Using the screen capture API](../screen_capture_api/using_screen_capture)
- [Capabilities, constraints, and settings](../media_streams_api/constraints)
- [`MediaDevices.getDisplayMedia()`](../mediadevices/getdisplaymedia)
- [`MediaStreamTrack.getConstraints()`](../mediastreamtrack/getconstraints)
- [`MediaStreamTrack.applyConstraints()`](../mediastreamtrack/applyconstraints)
- [`MediaStreamTrack.getSettings()`](../mediastreamtrack/getsettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/logicalSurface" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/logicalSurface</a>
