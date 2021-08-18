# MediaTrackSettings

The `MediaTrackSettings` dictionary is used to return the current values configured for each of a [`MediaStreamTrack`](mediastreamtrack)'s settings. These values will adhere as closely as possible to any constraints previously described using a [`MediaTrackConstraints`](mediatrackconstraints) object and set using [`applyConstraints()`](mediastreamtrack/applyconstraints), and will adhere to the default constraints for any properties whose constraints haven't been changed, or whose customized constraints couldn't be matched.

To learn more about how constraints and settings work, see [Capabilities, constraints, and settings](media_streams_api/constraints).

## Properties

Some or all of the following will be included in the object, either because it's not supported by the browser or because it's not available due to context. For example, because [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) doesn't provide some of these values during negotiation of a WebRTC connection, a track associated with a [`RTCPeerConnection`](rtcpeerconnection) will not include certain values, such as [`facingMode`](mediatracksettings/facingmode) or [`groupId`](mediatracksettings/groupid).

### Properties of all media tracks

[`deviceId`](mediatracksettings/deviceid)  
A [`DOMString`](domstring) indicating the current value of the `deviceId` property. The device ID is a origin-unique string identifying the source of the track; this is usually a <span class="page-not-created">GUID</span>. This value is specific to the source of the track's data and is not usable for setting constraints; it can, however, be used for initially selecting media when calling [`MediaDevices.getUserMedia()`](mediadevices/getusermedia).

[`groupId`](mediatracksettings/groupid)  
A [`DOMString`](domstring) indicating the current value of the `groupId` property. The group ID is a browsing session-unique string identifying the source group of the track. Two devices (as identified by the [`deviceId`](mediatracksettings/deviceid)) are considered part of the same group if they are from the same physical device. For instance, the audio input and output devices for the speaker and microphone built into a phone would share the same group ID, since they're part of the same physical device. The microphone on a headset would have a different ID, though. This value is specific to the source of the track's data and is not usable for setting constraints; it can, however, be used for initially selecting media when calling [`MediaDevices.getUserMedia()`](mediadevices/getusermedia).

### Properties of audio tracks

[`autoGainControl`](mediatracksettings/autogaincontrol)  
A Boolean which indicates the current value of the [`autoGainControl`](mediatrackconstraints/autogaincontrol) property, which is `true` if automatic gain control is enabled and is `false` otherwise.

[`channelCount`](mediatracksettings/channelcount)  
A long integer value indicating the current value of the `channelCount` property, specifying the number of audio channels present on the track (therefore indicating how many audio samples exist in each audio frame). This is 1 for mono, 2 for stereo, and so forth.

[`echoCancellation`](mediatracksettings/echocancellation)  
A Boolean indicating the current value of the `echoCancellation` property, specifying `true` if echo cancellation is enabled, otherwise `false`.

[`latency`](mediatracksettings/latency)  
A double-precision floating point value indicating the current value of the `latency` property, specifying the audio latency, in seconds. Latency is the amount of time which elapses between the start of processing the audio and the data being available to the next stop in the audio utilization process. This value is a target value; actual latency may vary to some extent for various reasons.

[`noiseSuppression`](mediatracksettings/noisesuppression)  
A Boolean which indicates the current value of the [`noiseSuppression`](mediatrackconstraints/noisesuppression) property, which is `true` if noise suppression is enabled and is `false` otherwise.

[`sampleRate`](mediatracksettings/samplerate)  
A long integer value indicating the current value of the `sampleRate` property, specifying the sample rate in samples per second of the audio data. Standard CD-quality audio, for example, has a sample rate of 41,000 samples per second.

[`sampleSize`](mediatracksettings/samplesize)  
A long integer value indicating the current value of the `sampleSize` property, specifying the linear size, in bits, of each audio sample. CD-quality audio, for example, is 16-bit, so this value would be 16 in that case.

[`volume`](mediatracksettings/volume)  
A double-precision floating point value indicating the current value of the `volume` property, specifying the volume level of the track. This value will be between 0.0 (silent) to 1.0 (maximum supported volume).

### Properties of video tracks

[`aspectRatio`](mediatracksettings/aspectratio)  
A double-precision floating point value indicating the current value of the `aspectRatio` property, specified precisely to 10 decimal places. This is the width of the image in pixels divided by its height in pixels. Common values include 1.3333333333 (for the classic television 4:3 "standard" aspect ratio, also used on tablets such as Apple's iPad), 1.7777777778 (for the 16:9 high-definition widescreen aspect ratio), and 1.6 (for the 16:10 aspect ratio common among widescreen computers and tablets).

[`facingMode`](mediatracksettings/facingmode)  
A [`DOMString`](domstring) indicating the current value of the `facingMode` property, specifying the direction the camera is facing. The value will be one of:

`"user"`  
A camera facing the user (commonly known as a "selfie cam"), used for self-portraiture and video calling.

`"environment"`  
A camera facing away from the user (when the user is looking at the screen). This is typically the highest quality camera on the device, used for general photography.

`"left"`  
A camera facing toward the environment to the user's left.

`"right"`  
A camera facing toward the environment to the user's right.

[`frameRate`](mediatracksettings/framerate)  
A double-precision floating point value indicating the current value of the `frameRate` property, specifying how many frames of video per second the track includes. If the value can't be determined for any reason, the value will match the vertical sync rate of the device the user agent is running on.

[`height`](mediatracksettings/height)  
A long integer value indicating the current value of the `height` property, specifying the height of the track's video data in pixels.

[`width`](mediatracksettings/width)  
A long integer value indicating the current value of the [`width`](mediatracksettings/width) property, specifying the width of the track's video data in pixels.

<span class="page-not-created">`resizeMode`</span>  
A [`DOMString`](domstring) indicating the current value of the `resizeMode` property, specifying the mode used by the user agent to derive the resolution of the track. The value will be one of:

`"none"`  
The track has the resolution offered by the camera, its driver or the OS.

`"crop-and-scale"`  
The track's resolution might be the result of the user agent using cropping or downscaling from a higher camera resolution.

### Properties of shared screen tracks

Tracks containing video shared from a user's screen (regardless of whether the screen data comes from the entire screen or a portion of a screen, like a window or tab) are generally treated like video tracks, with the exception that they also support the following added settings:

[`cursor`](mediatracksettings/cursor)  
A [`DOMString`](domstring) which indicates whether or not the mouse cursor is being included in the generated stream and under what conditions. Possible values are:

`always`  
The mouse is always visible in the video content of the {domxref("MediaStream"), unless the mouse has moved outside the area of the content.

`motion`  
The mouse cursor is always included in the video if it's moving, and for a short time after it stops moving.

`never`  
The mouse cursor is never included in the shared video.

[`displaySurface`](mediatracksettings/displaysurface)  
A [`DOMString`](domstring) which specifies the type of source the track contains; one of:

`application`  
The stream contains all of the windows of the application chosen by the user rendered into the one video track.

`browser`  
The stream contains the contents of a single browser tab selected by the user.

`monitor`  
The stream's video track contains the entire contents of one or more of the user's screens.

`window`  
The stream contains a single window selected by the user for sharing.

[`logicalSurface`](mediatracksettings/logicalsurface)  
A Boolean value which, if `true`, indicates that the video contained in the stream's video track contains a background rendering context, rather than a user-visible one. This is `false` if the video being captured is coming from a foreground (user-visible) source.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#media-track-settings">Media Capture and Streams<br />
<span class="small">The definition of 'MediaTrackSettings' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://w3c.github.io/mediacapture-screen-share/#extensions-to-mediatracksettings">Screen Capture<br />
<span class="small">The definition of 'MediaTrackSettings extensions' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Defines the <code>displaySurface</code>, <code>logicalSurface</code>, and <code>cursor</code> members</td></tr></tbody></table>

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

`MediaTrackSettings`

59

≤79

Yes

No

Yes

?

59

59

Yes

Yes

?

7.0

`aspectRatio`

Yes

≤79

No

No

Yes

?

Yes

Yes

No

Yes

?

Yes

`autoGainControl`

Yes

≤79

55

50-55

No

Yes

?

Yes

Yes

55

50-55

Yes

?

Yes

`channelCount`

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

`deviceId`

Yes

≤79

69

No

Yes

?

Yes

Yes

No

Yes

?

Yes

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

`echoCancellation`

Yes

≤79

50

No

Yes

?

Yes

Yes

50

Yes

?

Yes

`facingMode`

Yes

≤79

69

No

Yes

?

Yes

Yes

No

Yes

?

Yes

`frameRate`

Yes

≤79

36

No

Yes

?

Yes

Yes

36

Yes

?

Yes

`groupId`

Yes

≤79

69

No

Yes

?

Yes

Yes

No

Yes

?

Yes

`height`

Yes

≤79

36

No

Yes

?

Yes

Yes

36

Yes

?

Yes

`latency`

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

`noiseSuppression`

Yes

≤79

55

50-55

No

Yes

?

Yes

Yes

55

50-55

Yes

?

Yes

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

`sampleSize`

Yes

≤79

No

No

Yes

?

Yes

Yes

No

Yes

?

Yes

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

`width`

Yes

≤79

36

No

Yes

?

Yes

Yes

36

Yes

?

Yes

## See also

- [`MediaDevices.getUserMedia()`](mediadevices/getusermedia)
- [`MediaDevices.getDisplayMedia()`](mediadevices/getdisplaymedia)
- [`MediaStreamTrack.getConstraints()`](mediastreamtrack/getconstraints)
- [`MediaStreamTrack.applyConstraints()`](mediastreamtrack/applyconstraints)
- [`MediaStreamTrack.getSettings()`](mediastreamtrack/getsettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings</a>
