# MediaRecorder.mimeType

The `mimeType` read-only property returns the [MIME](https://developer.mozilla.org/en-US/docs/Glossary/mime) media type that was specified when creating the [`MediaRecorder`](../mediarecorder) object, or, if none was specified, which was chosen by the browser. This is the file format of the file that would result from writing all of the recorded data to disk.

Keep in mind that not all codecs are supported by a given container; if you write media using a codec that is not supported by a given media container, the resulting file may not work reliably if at all when you try to play it back. See our [media type and format guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats) for information about container and codec support across browsers.

**Note:** The term "MIME type" is officially considered to be historical; these strings are now officially known as **media types**. MDN Web Docs content uses the terms interchangeably.

## Syntax

    var mimeType = mediaRecorder.mimeType

### Value

The MIME media type which describes the format of the recorded media, as a [`DOMString`](../domstring). This string _may_ include the [`codecs` parameter,](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/codecs_parameter) giving details about the codecs and the codec configurations used by the media recorder.

The media type strings are standardized by the Internet Assigned Numbers Authority (IANA). For their official list of defined media type strings, see the article [Media Types](https://www.iana.org/assignments/media-types/media-types.xhtml) on the IANA site. See also [media types](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types) to learn more about media types and how they're used in web content and by web browsers.

## Example

    ...

    if (navigator.mediaDevices) {
      console.log('getUserMedia supported.');

      var constraints = { audio: true, video: true };
      var chunks = [];

      navigator.mediaDevices.getUserMedia(constraints)
        .then(function(stream) {
          var options = {
            audioBitsPerSecond: 128000,
            videoBitsPerSecond: 2500000,
            mimeType: 'video/mp4'
          }
          var mediaRecorder = new MediaRecorder(stream,options);
          m = mediaRecorder;

          m.mimeType; // would return 'video/mp4'
          ...
        })
        .catch(function(error) {
          console.log(error.message);
        });

Changing line 14 to the following causes `MediaRecorder` to try to use AVC Constrained Baseline Profile Level 4 for video and AAC-LC (Low Complexity) for audio, which is good for mobile and other possible resource-constrained situations.

    mimeType: 'video/mp4; codecs="avc1.424028, mp4a.40.2"'

Assuming this configuration is acceptable to the user agent, the value returned later by `m.mimeType` would then be `video/mp4; codecs="avc1.424028, mp4a.40.2"`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-mediarecorder-mimetype">MediaStream Recording<br />
<span class="small">The definition of 'MediaRecorder.mimeType' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`mimeType`

49

47-49

Prior to Chrome 49, only video is supported, not audio.

79

25

Starting with Firefox 71, the behavior of `mimeType` is more consistent. For example, it now returns the media type even after recording has stopped.

No

36

14

49

47-49

Prior to Chrome 49, only video is supported, not audio.

49

47-49

Prior to Chrome 49, only video is supported, not audio.

25

36

14

5.0

## See also

- [Using the MediaRecorder API](../mediastream_recording_api/using_the_mediastream_recording_api)
- [The "codecs" parameter in common media types](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/codecs_parameter)
- [Web Dictaphone](https://mdn.github.io/web-dictaphone/): MediaRecorder + getUserMedia + Web Audio API visualization demo, by [Chris Mills](https://twitter.com/chrisdavidmills) ([source on Github](https://github.com/mdn/web-dictaphone/).)
- [simpl.info MediaStream Recording demo](https://simpl.info/mediarecorder/), by [Sam Dutton](https://twitter.com/sw12).
- [`MediaDevices.getUserMedia()`](../mediadevices/getusermedia)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/mimeType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/mimeType</a>
