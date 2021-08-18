MediaTrackSupportedConstraints
==============================

The `MediaTrackSupportedConstraints` dictionary establishes the list of constrainable properties recognized by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) or browser in its implementation of the [`MediaStreamTrack`](mediastreamtrack) object. An object conforming to `MediaTrackSupportedConstraints` is returned by [`MediaDevices.getSupportedConstraints()`](mediadevices/getsupportedconstraints).

Because of the way interface definitions in WebIDL work, if a constraint is requested but not supported, no error will occur. Instead, the specified constraints will be applied, with any unrecognized constraints stripped from the request.That can lead to confusing and hard to debug errors, so be sure to use `getSupportedConstraints()` to retrieve this information before attempting to establish constraints if you need to know the difference between silently ignoring a constraint and a constraint being accepted.

An actual constraint set is described using an object based on the [`MediaTrackConstraints`](mediatrackconstraints) dictionary.

To learn more about how constraints work, see [Capabilities, constraints, and settings](media_streams_api/constraints).

Properties
----------

Some combination—but not necessarily all—of the following properties will exist on the object.

[`autoGainControl`](mediatracksupportedconstraints/autogaincontrol)  
A Boolean whose value is `true` if the `autoGainControl` constraint is supported in the current environment.

[`width`](mediatracksupportedconstraints/width)  
A Boolean value whose value is `true` if the `width` constraint is supported in the current environment.

[`height`](mediatracksupportedconstraints/height)  
A Boolean value whose value is `true` if the `height` constraint is supported in the current environment.

[`aspectRatio`](mediatracksupportedconstraints/aspectratio)  
A Boolean value whose value is `true` if the `aspectRatio` constraint is supported in the current environment.

[`frameRate`](mediatracksupportedconstraints/framerate)  
A Boolean value whose value is `true` if the `frameRate` constraint is supported in the current environment.

[`facingMode`](mediatracksupportedconstraints/facingmode)  
A Boolean value whose value is `true` if the `facingMode` constraint is supported in the current environment.

<span class="page-not-created">`resizeMode`</span>  
A Boolean value whose value is `true` if the `resizeMode` constraint is supported in the current environment.

[`volume`](mediatracksupportedconstraints/volume)  
A Boolean value whose value is `true` if the `volume` constraint is supported in the current environment.

[`sampleRate`](mediatracksupportedconstraints/samplerate)  
A Boolean value whose value is `true` if the `sampleRate` constraint is supported in the current environment.

[`sampleSize`](mediatracksupportedconstraints/samplesize)  
A Boolean value whose value is `true` if the `sampleSize` constraint is supported in the current environment.

[`echoCancellation`](mediatracksupportedconstraints/echocancellation)  
A Boolean value whose value is `true` if the `echoCancellation` constraint is supported in the current environment.

[`latency`](mediatracksupportedconstraints/latency)  
A Boolean value whose value is `true` if the `latency` constraint is supported in the current environment.

[`noiseSuppression`](mediatracksupportedconstraints/noisesuppression)  
A Boolean whose value is `true` if the `noiseSuppression` constraint is supported in the current environment.

[`channelCount`](mediatracksupportedconstraints/channelcount)  
A Boolean value whose value is `true` if the `channelCount` constraint is supported in the current environment.

[`deviceId`](mediatracksupportedconstraints/deviceid)  
A Boolean value whose value is `true` if the `deviceId` constraint is supported in the current environment.

[`groupId`](mediatracksupportedconstraints/groupid)  
A Boolean value whose value is `true` if the `groupId` constraint is supported in the current environment.

### Properties specific to shared screen tracks

For tracks containing video sources from the user's screen contents, the following additional properties are may be included in addition to those available for video tracks.

[`cursor`](mediatracksupportedconstraints/cursor)  
A Boolean value which is `true` if the [`cursor`](mediatrackconstraints/cursor) constraint is supported in the current environment.

[`displaySurface`](mediatracksupportedconstraints/displaysurface)  
A Boolean value which is `true` if the [`cursor`](mediatrackconstraints/displaysurface) constraint is supported in the current environment.

[`logicalSurface`](mediatracksupportedconstraints/logicalsurface)  
A Boolean value which is `true` if the [`logicalSurface`](mediatrackconstraints/logicalsurface) constraint is supported in the current environment.

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

`MediaTrackSupportedConstraints`

52

≤79

42

No

Yes

?

52

52

42

Yes

?

6.0

`aspectRatio`

52

≤79

No

No

Yes

?

52

52

No

Yes

?

6.0

`autoGainControl`

69

≤79

55

Yes-55

No

Yes

?

69

69

55

Yes-55

Yes

?

10.0

`channelCount`

52

≤79

56

No

Yes

?

52

52

56

Yes

?

6.0

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

52

≤79

42

No

Yes

?

52

52

42

Yes

?

6.0

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

52

≤79

46

No

Yes

?

52

52

46

Yes

?

6.0

`facingMode`

52

≤79

42

No

Yes

?

52

52

42

Yes

?

6.0

`frameRate`

52

≤79

42

No

Yes

?

52

52

42

Yes

?

6.0

`groupId`

52

≤79

70

No

Yes

?

52

52

No

Yes

?

6.0

`height`

52

≤79

42

No

Yes

?

52

52

42

Yes

?

6.0

`latency`

52

≤79

No

No

Yes

?

52

52

No

Yes

?

6.0

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

69

≤79

55

Yes-55

No

Yes

?

69

69

55

Yes-55

Yes

?

10.0

`resizeMode`

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

`sampleRate`

52

≤79

No

No

Yes

?

52

52

No

Yes

?

6.0

`sampleSize`

52

≤79

No

No

Yes

?

52

52

No

Yes

?

6.0

`volume`

52

≤79

No

No

Yes

?

52

52

No

Yes

?

6.0

`width`

52

≤79

42

No

Yes

?

52

52

42

Yes

?

6.0

See also
--------

-   [Media Capture and Streams API](media_streams_api)
-   [Capabilities, constraints, and settings](media_streams_api/constraints)
-   [Screen Capture API](screen_capture_api)
-   [Using the Screen Capture API](screen_capture_api/using_screen_capture)
-   [`MediaTrackConstraints`](mediatrackconstraints)
-   [`MediaDevices.getUserMedia()`](mediadevices/getusermedia)
-   [`MediaStreamTrack.getConstraints()`](mediastreamtrack/getconstraints)
-   [`MediaStreamTrack.applyConstraints()`](mediastreamtrack/applyconstraints)
-   [`MediaStreamTrack.getSettings()`](mediastreamtrack/getsettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints</a>
