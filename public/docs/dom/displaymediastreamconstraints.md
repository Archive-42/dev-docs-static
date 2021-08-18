# DisplayMediaStreamConstraints

The `DisplayMediaStreamConstraints` dictionary is used to specify whether or not to include video and/or audio tracks in the [`MediaStream`](mediastream) to be returned by [`getDisplayMedia()`](mediadevices/getdisplaymedia), as well as what type of processing must be applied to the tracks. Processing information is specified using [`MediaTrackConstraints`](mediatrackconstraints) objects providing options which are applied to the track after the media data is received but before it is made available on the [`MediaStream`](mediastream).

## Properties

[`audio`](displaymediastreamconstraints/audio)  
A Boolean or [`MediaTrackConstraints`](mediatrackconstraints) value; if a Boolean, this value indicates whether or not to include an audio track in the [`MediaStream`](mediastream) returned by [`getDisplayMedia()`](mediadevices/getdisplaymedia). If a `MediaTrackConstraints` object is provided here, an audio track is included in the stream, but the audio is processed to match the specified constraints after being retrieved from the hardware but before being added to the [`MediaStream`](mediastream). The default value is `false`.

[`video`](displaymediastreamconstraints/video)  
If `true` (the default), the display contents are included in a [`MediaStreamTrack`](mediastreamtrack) within the stream provided by `getDisplayMedia()`. Optionally, a [`MediaTrackConstraints`](mediatrackconstraints) object may be given, providing options specifying processing to be performed on the video data before adding it to the stream. A value of `false` is not permitted, and results in a `TypeError` being thrown.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-screen-share/#dom-displaymediastreamconstraints">Screen Capture<br />
<span class="small">The definition of 'DisplayMediaStreamConstraints' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.DisplayMediaStreamConstraints`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Screen Capture API](screen_capture_api)
- [Using the Screen Capture API](screen_capture_api/using_screen_capture)
- [Capabilities, constraints, and settings](media_streams_api/constraints)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DisplayMediaStreamConstraints" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DisplayMediaStreamConstraints</a>
