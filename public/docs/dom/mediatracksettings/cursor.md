MediaTrackSettings.cursor
=========================

The [`MediaTrackSettings`](../mediatracksettings) dictionary's `cursor` property indicates whether or not the cursor should be captured as part of the video track included in the [`MediaStream`](../mediastream) returned by [`getDisplayMedia()`](../mediadevices/getdisplaymedia).

Syntax
------

    cursorSetting = mediaTrackSettings.cursor;

### Value

The value of `cursor` comes from the `CursorCaptureConstraint` enumerated string type, and may have one of the following values:

`always`  
The mouse should always be visible in the video content of the [`MediaStream`](../mediastream), unless the mouse has moved outside the area of the content.

`motion`  
The mouse cursor should always be included in the video if it's moving, and for a short time after it stops moving.

`never`  
The mouse cursor is never included in the shared video.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-screen-share/#dom-mediatracksettings-cursor">Screen Capture<br />
<span class="small">The definition of 'MediaTrackSettings.cursor' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

-   [Screen Capture API](../screen_capture_api)
-   [Using the screen capture API](../screen_capture_api/using_screen_capture)
-   [Capabilities, constraints, and settings](../media_streams_api/constraints)
-   [`MediaDevices.getDisplayMedia()`](../mediadevices/getdisplaymedia)
-   [`MediaStreamTrack.getConstraints()`](../mediastreamtrack/getconstraints)
-   [`MediaStreamTrack.applyConstraints()`](../mediastreamtrack/applyconstraints)
-   [`MediaStreamTrack.getSettings()`](../mediastreamtrack/getsettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/cursor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/cursor</a>
