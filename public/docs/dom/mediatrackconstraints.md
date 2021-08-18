MediaTrackConstraints
=====================

The `MediaTrackConstraints` dictionary is used to describe a set of capabilities and the value or values each can take on. A constraints dictionary is passed into [`applyConstraints()`](mediastreamtrack/applyconstraints) to allow a script to establish a set of exact (required) values or ranges and/or preferred values or ranges of values for the track, and the most recently-requested set of custom constraints can be retrieved by calling [`getConstraints()`](mediastreamtrack/getconstraints).

For each constraint, you can typically specify an exact value you need, an ideal value you want, a range of acceptable values, and/or a value which you'd like to be as close to as possible. The specifics vary somewhat depending on the type of the constrainable property.

To learn more about how constraints work, see [Capabilities, constraints, and settings](media_streams_api/constraints).

Properties
----------

Some combination—but not necessarily all—of the following properties will exist on the object. This may be because a given browser doesn't support the property, or because it doesn't apply. For example, because [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) doesn't provide some of these values during negotiation of a WebRTC connection, a track associated with a [`RTCPeerConnection`](rtcpeerconnection) will not include certain values, such as [`facingMode`](mediatrackconstraints/facingmode) or [`groupId`](mediatrackconstraints/groupid).

### Properties of all media tracks

[`deviceId`](mediatrackconstraints/deviceid)  
A [`ConstrainDOMString`](constraindomstring) object specifying a device ID or an array of device IDs which are acceptable and/or required.

[`groupId`](mediatrackconstraints/groupid)  
A [`ConstrainDOMString`](constraindomstring) object specifying a group ID or an array of group IDs which are acceptable and/or required.

### Properties of audio tracks

[`autoGainControl`](mediatrackconstraints/autogaincontrol)  
A [`ConstrainBoolean`](constrainboolean) object which specifies whether automatic gain control is preferred and/or required.

[`channelCount`](mediatrackconstraints/channelcount)  
A [`ConstrainULong`](constrainulong) specifying the channel count or range of channel counts which are acceptable and/or required.

[`echoCancellation`](mediatrackconstraints/echocancellation)  
A [`ConstrainBoolean`](constrainboolean) object specifying whether or not echo cancellation is preferred and/or required.

[`latency`](mediatrackconstraints/latency)  
A [`ConstrainDouble`](constraindouble) specifying the latency or range of latencies which are acceptable and/or required.

[`noiseSuppression`](mediatrackconstraints/noisesuppression)  
A [`ConstrainBoolean`](constrainboolean) which specifies whether noise suppression is preferred and/or required.

[`sampleRate`](mediatrackconstraints/samplerate)  
A [`ConstrainULong`](constrainulong) specifying the sample rate or range of sample rates which are acceptable and/or required.

[`sampleSize`](mediatrackconstraints/samplesize)  
A [`ConstrainULong`](constrainulong) specifying the sample size or range of sample sizes which are acceptable and/or required.

[`volume`](mediatrackconstraints/volume)  
A [`ConstrainDouble`](constraindouble) specifying the volume or range of volumes which are acceptable and/or required.

### Properties of image tracks

<span id="whitebalancemode">whiteBalanceMode</span>  
A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) specifying one of `"none"`, `"manual"`, `"single-shot"`, or `"continuous"`.

<span id="exposuremode">exposureMode</span>  
A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) specifying one of `"none"`, `"manual"`, `"single-shot"`, or `"continuous"`.

<span id="focusmode">focusMode</span>  
A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) specifying one of `"none"`, `"manual"`, `"single-shot"`, or `"continuous"`.

<span id="pointsofinterest">pointsOfInterest</span>  
The pixel coordinates on the sensor of one or more points of interest. This is either an object in the form { x:*value*, y:*value* } or an array of such objects, where *value* is a double-precision integer.

<span id="exposurecompensation">exposureCompensation</span>  
A [`ConstrainDouble`](constraindouble) (a double-precision integer) specifying f-stop adjustment by up to ±3.

<span id="colortemperature">colorTemperature</span>  
A [`ConstrainDouble`](constraindouble) (a double-precision integer) specifying a desired color temperature in degrees kelvin.

<span id="iso">iso</span>  
A [`ConstrainDouble`](constraindouble) (a double-precision integer) specifying a desired iso setting.

<span id="brightness">brightness</span>  
A [`ConstrainDouble`](constraindouble) (a double-precision integer) specifying a desired brightness setting.

<span id="contrast">contrast</span>  
A [`ConstrainDouble`](constraindouble) (a double-precision integer) specifying the degree of difference between light and dark.

<span id="saturation">saturation</span>  
A [`ConstrainDouble`](constraindouble) (a double-precision integer) specifying the degree of color intensity.

<span id="sharpness">sharpness</span>  
A [`ConstrainDouble`](constraindouble) (a double-precision integer) specifying the intensity of edges.

<span id="focusdistance">focusDistance</span>  
A [`ConstrainDouble`](constraindouble) (a double-precision integer) specifying distance to a focused object.

<span id="zoom">zoom</span>  
A [`ConstrainDouble`](constraindouble) (a double-precision integer) specifying the desired focal length.

<span id="torch">torch</span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) defining whether the fill light is continuously connected, meaning it stays on as long as the track is active.

### Properties of video tracks

[`aspectRatio`](mediatrackconstraints/aspectratio)  
A [`ConstrainDouble`](constraindouble) specifying the video aspect ratio or range of aspect ratios which are acceptable and/or required.

[`facingMode`](mediatrackconstraints/facingmode)  
A [`ConstrainDOMString`](constraindomstring) object specifying a facing or an array of facings which are acceptable and/or required.

[`frameRate`](mediatrackconstraints/framerate)  
A [`ConstrainDouble`](constraindouble) specifying the frame rate or range of frame rates which are acceptable and/or required.

[`height`](mediatrackconstraints/height)  
A [`ConstrainULong`](constrainulong) specifying the video height or range of heights which are acceptable and/or required.

[`width`](mediatrackconstraints/width)  
A [`ConstrainULong`](constrainulong) specifying the video width or range of widths which are acceptable and/or required.

<span id="resizemode">resizeMode</span>  
A [`ConstrainDOMString`](constraindomstring) object specifying a mode or an array of modes the UA can use to derive the resolution of a video track. Allowed values are `none` and `crop-and-scale`. `none` means that the user agent uses the resolution provided by the camera, its driver or the OS. `crop-and-scale` means that the user agent can use cropping and downscaling on the camera output in order to satisfy other constraints that affect the resolution.

### Properties of shared screen tracks

These constraints apply to `MediaTrackConstraints` objects specified as part of the [`DisplayMediaStreamConstraints`](displaymediastreamconstraints) object's [`video`](displaymediastreamconstraints/video) property when using [`getDisplayMedia()`](mediadevices/getdisplaymedia) to obtain a stream for screen sharing.

[`cursor`](mediatrackconstraints/cursor)  
A [`ConstrainDOMString`](constraindomstring) which specifies whether or not to include the mouse cursor in the generated track, and if so, whether or not to hide it while not moving. The value may be a single one of the following strings, or an array of them to allow the browser flexibility in deciding what to do about the cursor.

`always`  
The mouse is always visible in the video content of the {domxref("MediaStream"), unless the mouse has moved outside the area of the content.

`motion`  
The mouse cursor is always included in the video if it's moving, and for a short time after it stops moving.

`never`  
The mouse cursor is never included in the shared video.

[`displaySurface`](mediatrackconstraints/displaysurface)  
A [`ConstrainDOMString`](constraindomstring) which specifies the types of display surface that may be selected by the user. This may be a single one of the following strings, or a list of them to allow multiple source surfaces:

`application`  
The stream contains all of the windows of the application chosen by the user rendered into the one video track.

`browser`  
The stream contains the contents of a single browser tab selected by the user.

`monitor`  
The stream's video track contains the entire contents of one or more of the user's screens.

`window`  
The stream contains a single window selected by the user for sharing.

[`logicalSurface`](mediatrackconstraints/logicalsurface)  
A [`ConstrainBoolean`](constrainboolean) value which may contain a single Boolean value or a set of them, indicating whether or not to allow the user to choose source surfaces which do not directly correspond to display areas. These may include backing buffers for windows to allow capture of window contents that are hidden by other windows in front of them, or buffers containing larger documents that need to be scrolled through to see the entire contents in their windows.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatrackconstraints">Media Capture and Streams</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/mediacapture-image/#mediatrackconstraintset-section">MediaStream Image Capture</a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds image constraints.</td></tr></tbody></table>

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

`MediaTrackConstraints`

59

≤18

Yes

No

46

?

59

Yes

Yes

43

?

Yes

`aspectRatio`

59

≤79

No

No

Yes

?

59

59

29

?

?

7.0

`autoGainControl`

Yes

≤79

55

46

No

Yes

?

Yes

Yes

55

46

?

?

Yes

`channelCount`

59

≤79

No

No

Yes

?

59

59

No

?

?

7.0

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

`deviceId`

59

≤79

36

Prior to Firefox 69, Firefox only supported `deviceId` in constraints passed into `getUserMedia()`.

No

Yes

?

59

59

36

Firefox for Android only supports `deviceId` when used in constraints passed into `getUserMedia()`.

?

?

7.0

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

`echoCancellation`

59

≤79

50

No

Yes

?

59

59

50

?

?

7.0

`facingMode`

59

≤79

50

No

Yes

?

59

59

50

?

?

7.0

`frameRate`

59

≤79

50

No

Yes

?

59

59

50

?

?

7.0

`groupId`

59

≤79

70

No

Yes

?

59

59

No

?

?

7.0

`height`

59

≤79

50

No

Yes

?

59

59

50

?

?

7.0

`latency`

59

≤79

50

No

Yes

?

59

59

50

?

?

7.0

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

`noiseSuppression`

Yes

≤79

55

46

No

Yes

?

Yes

Yes

55

46

?

?

Yes

`sampleRate`

59

≤79

No

No

Yes

?

59

59

No

?

?

7.0

`sampleSize`

59

≤79

No

No

Yes

?

59

59

No

?

?

7.0

`volume`

59

≤79

No

No

Yes

?

59

59

No

?

?

7.0

`width`

59

≤79

50

No

Yes

?

59

59

50

?

?

7.0

See also
--------

-   [Media Capture and Streams API](media_streams_api)
-   [Capabilities, constraints, and settings](media_streams_api/constraints)
-   [Screen Capture API](screen_capture_api)
-   [Using the Screen Capture API](screen_capture_api/using_screen_capture)
-   [`MediaDevices.getUserMedia()`](mediadevices/getusermedia)
-   [`MediaStreamTrack.getConstraints()`](mediastreamtrack/getconstraints)
-   [`MediaStreamTrack.applyConstraints()`](mediastreamtrack/applyconstraints)
-   [`MediaDevices.getSupportedConstraints()`](mediadevices/getsupportedconstraints)
-   [`MediaTrackSupportedConstraints`](mediatracksupportedconstraints)
-   [`MediaStreamTrack.getSettings()`](mediastreamtrack/getsettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints</a>
