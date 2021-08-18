# DisplayMediaStreamConstraints.video

The [`DisplayMediaStreamConstraints`](../displaymediastreamconstraints) dictionary's `video` property is used to configure the video track in the stream returned by [`getDisplayMedia()`](../mediadevices/getdisplaymedia). This value may be a Boolean, where `true` specifies that a default selection of input source be made (typically the entire display area of the device in use, spanning every screen in a multiple screen configuration). Since a video track must always be included, a value of `false` results in a `TypeError` exception being thrown.

More precise control over the format of the returned video track may be exercised by instead providing a [`MediaTrackConstraints`](../mediatrackconstraints) object, which is used to process the video data after obtaining it from the device but prior to adding it to the stream.

## Syntax

    displayMediaStreamConstraints.video = allowVideoFlag;
    displayMediaStreamConstraints.video = mediaTrackConstraints;

    displayMediaStreamConstraints = {
      video: allowVideoFlag | mediaTrackConstraints;
    }

### Value

The value may be either a Boolean or a [`MediaTrackConstraints`](../mediatrackconstraints) object.

If a Boolean is specified, a value of `true` (the default) indicates that the stream returned by [`getDisplayMedia()`](../mediadevices/getdisplaymedia) should be in whatever format the user agent feels is best. A value of `false` is not permitted and will throw a `TypeError`.

If a `MediaTrackConstraints` object is given instead, the video track will be processed to match the settings given in the constraints object.

## Constraints specific to screen sharing

{{page("/en-US/docs/Web/API/MediaTrackConstraints", "Properties of shared screen tracks")}}

## Example

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-screen-share/#dom-displaymediastreamconstraints-video">Screen Capture<br />
<span class="small">The definition of 'DisplayMediaStreamConstraints.video' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.DisplayMediaStreamConstraints.video`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Screen Capture API](../screen_capture_api)
- [Using the Screen Capture API](../screen_capture_api/using_screen_capture)
- [Capabilities, constraints, and settings](../media_streams_api/constraints)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DisplayMediaStreamConstraints/video" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DisplayMediaStreamConstraints/video</a>
