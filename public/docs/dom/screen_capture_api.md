Screen Capture API
==================

The Screen Capture API introduces additions to the existing Media Capture and Streams API to let the user select a screen or portion of a screen (such as a window) to capture as a media stream. This stream can then be recorded or shared with others over the network.

Screen Capture API concepts and usage
-------------------------------------

The Screen Capture API is relatively simple to use. Its sole method is [`MediaDevices.getDisplayMedia()`](mediadevices/getdisplaymedia), whose job is to ask the user to select a screen or portion of a screen to capture in the form of a [`MediaStream`](mediastream).

To start capturing video from the screen, you call `getDisplayMedia()` on the instance of `Media` `navigator.mediaDevices`:

    captureStream = await navigator.mediaDevices.getDisplayMedia(displayMediaOptions);

The [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by `getDisplayMedia()` resolves to a [`MediaStream`](mediastream) which streams the captured media.

See the article [Using the Screen Capture API](screen_capture_api/using_screen_capture) for a more in-depth look at how to use the API to capture screen contents as a stream.

Additions to existing interfaces
--------------------------------

The Screen Capture API doesn't have any interfaces of its own; instead, it adds one method to the existing [`MediaDevices`](mediadevices) interface.

### MediaDevices interface

[`MediaDevices.getDisplayMedia()`](mediadevices/getdisplaymedia)  
The `getDisplayMedia()` method is added to the `MediaDevices` interface. Similar to [`getUserMedia()`](mediadevices/getusermedia), this method creates a promise that resolves with a [`MediaStream`](mediastream) containing the display area selected by the user, in a format that matches the specified options.

Additions to existing dictionaries
----------------------------------

The Screen Capture API adds properties to the following dictionaries defined by other specifications.

### MediaTrackConstraints

[`MediaTrackConstraints.cursor`](mediatrackconstraints/cursor)  
A [`ConstrainDOMString`](constraindomstring) indicating whether or not the cursor should be included in the captured display surface's stream, and if it should always be visible or if it should only be visible while the mouse is in motion.

[`MediaTrackConstraints.displaySurface`](mediatrackconstraints/displaysurface)  
A [`ConstrainDOMString`](constraindomstring) indicating what type of display surface is to be captured. The value is one of `application`, `browser`, `monitor`, or `window`.

[`MediaTrackConstraints.logicalSurface`](mediatrackconstraints/logicalsurface)  
Indicates whether or not the video in the stream represents a logical display surface (that is, one which may not be entirely visible onscreen, or may be completely offscreen). A value of `true` indicates a logical display surface is to be captured.

### MediaTrackSettings

[`MediaTrackSettings.cursor`](mediatracksettings/cursor)  
A string which indicates whether or not the display surface currently being captured includes the mouse cursor, and if so, whether it's only visible while the mouse is in motion or if it's always visible. The value is one of `always`, `motion`, or `never`.

[`MediaTrackSettings.displaySurface`](mediatracksettings/displaysurface)  
A string indicating what type of display surface is currently being captured. The value is one of `application`, `browser`, `monitor`, or `window`.

[`MediaTrackSettings.logicalSurface`](mediatracksettings/logicalsurface)  
A Boolean value which is `true` if the video being captured doesn't directly correspond to a single onscreen display area.

### MediaTrackSupportedConstraints

[`MediaTrackSupportedConstraints.cursor`](mediatracksupportedconstraints/cursor)  
A Boolean which is `true` if the user agent and device support the [`MediaTrackConstraints.cursor`](mediatrackconstraints/cursor) constraint.

[`MediaTrackSupportedConstraints.displaySurface`](mediatracksupportedconstraints/displaysurface)  
A Boolean which is `true` if the current environment supports the [`MediaTrackConstraints.displaySurface`](mediatrackconstraints/displaysurface) constraint.

[`MediaTrackSupportedConstraints.logicalSurface`](mediatracksupportedconstraints/logicalsurface)  
A Boolean which is `true` if the current environment supports the constraint [`MediaTrackConstraints.logicalSurface`](mediatrackconstraints/logicalsurface).

Dictionaries
------------

The following dictionaries are defined by the Screen Capture API.

`CursorCaptureConstraint`  
An enumerated string type used to provide the value for the `cursor` property for the settings and constraints. The possible values are `always`, `motion`, and `never`.

`DisplayCaptureSurfaceType`  
An enumerated string type which is used to identify the kind of display surface to capture. This type is used for the `displaySurface` property in the constraints and settings objects, and has the possible values `application`, `browser`, `monitor`, and `window`.

Feature Policy validation
-------------------------

[User agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) that support Feature Policy (either using HTTP's [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) header or the [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) attribute [`allow`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-allow)) can specify a desire to use the Screen Capture API using the policy control directive `display-capture`:

    <iframe allow="display-capture" src="/some-other-document.html">

The default allow list is `self`, which lets the any content within the document use Screen Capture.

See [Using Feature Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy/Using_Feature_Policy) for a more in-depth explanation of how Feature Policy is used.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-screen-share/">Screen Capture</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`Screen_Capture_API`

72

79

17

Available as a member of `Navigator` instead of `MediaDevices`.

66

33-66

Since Firefox 33 you can capture screen data using `getUserMedia()`, with a `video` constraint called `mediaSource`. Prior to 52 it relied on a client-configurable list of allowed sites.

No

60

13

No

API is available, but will always fail with `NotAllowedError`.

No

No

API is available, but will always fail with `NotAllowedError`.

No

No

No

`audio-capture-support`

74

On Windows and Chrome OS the entire system audio can be captured, but on Linux and Mac only the audio of a tab can be captured.

≤79

On Windows, the entire system audio can be captured, but on Linux and Mac only the audio of a tab can be captured.

No

No

?

No

No

No

No

No

No

No

See also
--------

-   [Using the Screen Capture API](screen_capture_api/using_screen_capture)
-   [`MediaDevices.getDisplayMedia()`](mediadevices/getdisplaymedia)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Screen_Capture_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Screen_Capture_API</a>
