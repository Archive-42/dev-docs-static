# MediaTrackSettings.displaySurface

The [`MediaTrackSettings`](../mediatracksettings) dictionary's `displaySurface` property indicates the type of display surface being captured.

## Syntax

    displaySurface = mediaTrackSettings.displaySurface;

### Value

The value of `displaySurface` is a string that comes from the `DisplayCaptureSurfaceType` enumerated type, and is one of the following:

`application`  
The stream's video track contains all of the windows belonging to the application chosen by the user. The windows are aggragated into a single video track, with any empty space filled with a backdrop; that backdrop is selected by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

`browser`  
The stream's video track presents the entire contents of a single browser tab which the user selected during the [`getDisplayMedia()`](../mediadevices/getdisplaymedia) call.

`monitor`  
The video track in the stream presents the complete contents of one or more of the user's screens. Any empty space (if the displays are of different dimensions) is filled with a backdrop chosen by the user agent.

`window`  
The stream's video track presents the contents of a single window selected by the user. The window may be from any application, not necessarily just from within the user agent.

Not all user agents support all of these surface types.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-screen-share/#dom-mediatrackconstraintset-displaysurface">Screen Capture<br />
<span class="small">The definition of 'MediaTrackSettings.displaySurface' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`displaySurface`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/displaySurface" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/displaySurface</a>
