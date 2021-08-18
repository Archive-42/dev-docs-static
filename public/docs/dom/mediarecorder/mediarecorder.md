# MediaRecorder()

The `MediaRecorder()` constructor creates a new [`MediaRecorder`](../mediarecorder) object that will record a specified [`MediaStream`](../mediastream). The object can optionally be configured to record using a specific media container (file type), and, further, can specify the exact codec and codec configuration(s) to use by specifying [the `codecs` parameter](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/codecs_parameter).

## Syntax

    var mediaRecorder = new MediaRecorder(stream[, options]);

### Parameters

`stream`

The [`MediaStream`](../mediastream) that will be recorded. This source media can come from a stream created using [`navigator.mediaDevices.getUserMedia()`](../mediadevices/getusermedia) or from an [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio), [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) or [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element.

`options`<span class="badge inline optional">Optional</span>

A dictionary object that can contain the following properties:

- `mimeType`: A MIME type specifying the format for the resulting media; you may specify the container format (the browser will select its preferred codecs for audio and/or video), or you may [use the `codecs` parameter](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/codecs_parameter) and/or the `profiles` parameter to provide detailed information about which codecs to use and how to configure them. Applications can check in advance if a `mimeType` is supported by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) by calling [`MediaRecorder.isTypeSupported()`](istypesupported).
- `audioBitsPerSecond`: The chosen bitrate for the audio component of the media.
- `videoBitsPerSecond`: The chosen bitrate for the video component of the media.
- `bitsPerSecond`: The chosen bitrate for the audio and video components of the media. This can be specified instead of the above two properties. If this is specified along with one or the other of the above properties, this will be used for the one that isn't specified.

If bits per second values are not specified for video and/or audio, the default adopted for video is 2.5Mbps, while the audio default is adaptive, depending upon the sample rate and the number of channels.

Video resolution, frame rate and similar settings are specified as constraints when calling [`getUserMedia()`](../mediadevices/getusermedia), not here in the MediaRecorder API.

### Exceptions

`NotSupportedError`  
The specified MIME type is not supported by the user agent.

## Example

This example shows how to create a media recorder for a specified stream, whose audio bit rate is set to 128 Kbit/sec and whose video bit rate is set to 2.5 Mbit/sec. The recorded media data will be stored in an MP4 wrapper (so if you gather the chunks of media data and save them to disk, they will be in an MP4 file).

    ...
    if (navigator.mediaDevices.getUserMedia) {
      var constraints = { audio: true, video: true };
      var chunks = [];

      var onSuccess = function(stream) {
        var options = {
          audioBitsPerSecond : 128000,
          videoBitsPerSecond : 2500000,
          mimeType : 'video/mp4'
        }
        var mediaRecorder = new MediaRecorder(stream,options);
        m = mediaRecorder;

    ...
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/">MediaStream Recording</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`MediaRecorder`

47

79

25

No

36

14

47

47

25

36

14

5.0

`options`

49

79

43

No

36

14

49

49

?

36

14

5.0

## See also

- [Using the MediaRecorder API](../mediastream_recording_api/using_the_mediastream_recording_api)
- [Web Dictaphone](https://mdn.github.io/web-dictaphone/): MediaRecorder + getUserMedia + Web Audio API visualization demo, by [Chris Mills](https://twitter.com/chrisdavidmills) ([source on Github](https://github.com/mdn/web-dictaphone/).)
- [simpl.info MediaStream Recording demo](https://simpl.info/mediarecorder/), by [Sam Dutton](https://twitter.com/sw12).
- [`MediaDevices.getUserMedia`](../mediadevices/getusermedia)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/MediaRecorder" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/MediaRecorder</a>
