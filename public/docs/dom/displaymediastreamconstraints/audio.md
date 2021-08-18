# DisplayMediaStreamConstraints.audio

The [`DisplayMediaStreamConstraints`](../displaymediastreamconstraints) dictionary's `audio` property is used to specify whether or not to request that the [`MediaStream`](../mediastream) containing screen display contents also include an audio track. This value may be a Boolean, where `true` indicates that an audio track should be included an `false` (the default) indicates that no audio should be included in the stream.

More precise control over the audio data may be exercised by instead providing a [`MediaTrackConstraints`](../mediatrackconstraints) object, which is used to process the audio prior to adding it to the stream.

**Note:** The specification for the Screen Capture API does not define what the contents of the audio track should be. This is left up to the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) to decide. Likely sources are the computer's system audio output and the user's microphone, but there is no way to specify which source to use.

## Syntax

    displayMediaStreamConstraints.audio = allowAudioFlag;
    displayMediaStreamConstraints.audio = mediaTrackConstraints;

    displayMediaStreamConstraints = {
      audio: allowAudioFlag|mediaTrackConstraints;
    }

### Value

The value may be either a Boolean or a [`MediaTrackConstraints`](../mediatrackconstraints) object.

If a Boolean is specified, a value of `true` indicates that an audio track should be included in the stream returned by [`getDisplayMedia()`](../mediadevices/getdisplaymedia), if an appropriate audio source exists and the user agent supports audio on display media. A value of `false`—the default—indicates that no audio track is to be included in the stream.

If a `MediaTrackConstraints` object is given, and an audio source is available, an audio track matching the settings given in the constraints object is included in the [`MediaStream`](../mediastream) returned by `getDisplayMedia()`.

If no audio source is available, or the user agent doesn't support audio tracks with `getDisplayMedia()`, the returned `MediaStream` has no audio track, but no error occurs. The audio track is always considered optional.

## Example

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-screen-share/#dom-displaymediastreamconstraints-audio">Screen Capture<br />
<span class="small">The definition of 'DisplayMediaStreamConstraints.audio' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.DisplayMediaStreamConstraints.audio`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Screen Capture API](../screen_capture_api)
- [Using the Screen Capture API](../screen_capture_api/using_screen_capture)
- [Capabilities, constraints, and settings](../media_streams_api/constraints)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DisplayMediaStreamConstraints/audio" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DisplayMediaStreamConstraints/audio</a>
