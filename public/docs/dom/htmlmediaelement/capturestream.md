# HTMLMediaElement.captureStream()

The `captureStream()` property of the [`HTMLMediaElement`](../htmlmediaelement) interface returns a [`MediaStream`](../mediastream) object which is streaming a real-time capture of the content being rendered in the media element.

This can be used, for example, as a source for a [WebRTC](../webrtc_api) [`RTCPeerConnection`](../rtcpeerconnection).

## Syntax

    var mediaStream = mediaElement.captureStream()

### Parameters

None.

### Return value

A [`MediaStream`](../mediastream) object which can be used as a source for audio and/or video data by other media processing code, or as a source for [WebRTC](https://developer.mozilla.org/en-US/docs/Glossary/WebRTC).

## Example

In this example, an event handler is established so that clicking a button starts capturing the contents of a media element with the ID `"playback"` into a [`MediaStream`](../mediastream). The stream can then be used for other purposes—like a source for streaming over WebRTC, to allow sharing prerecorded videos with another person during a video call.

    document.querySelector('.playAndRecord').addEventListener('click', function() {
      var playbackElement = document.getElementById("playback");
      var captureStream = playbackElement.captureStream();
      playbackElement.play();
    });

See [Recording a media element](../mediastream_recording_api/recording_a_media_element) for a longer and more intricate example and explanation.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-fromelement/#dom-htmlmediaelement-capturestream">Media Capture from DOM Elements<br />
<span class="small">The definition of 'captureStream()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`captureStream`

62

79

15

No

49

No

62

62

15

46

No

8.0

Prior to Firefox 51, you couldn't use `captureStream()` on a media element whose source is, itself, a [`MediaStream`](../mediastream) (like a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element which is presenting a stream being received over a [`RTCPeerConnection`](../rtcpeerconnection)). Beginning in Firefox 51, this works. This means you can capture a stream from the video element and use [`MediaRecorder`](../mediarecorder) to record it. See [bug 1259788](https://bugzilla.mozilla.org/show_bug.cgi?id=1259788) for details.

However, `captureStream()` is still prefixed as `mozCaptureStream()` on Firefox for good reason: there are some quirks in the present implementation which are worth noting:

- The Firefox implementation currently only works as described in the specification when the media element's source is, itself, a [`MediaStream`](../mediastream).
- If the media element's source isn't a `MediaStream`, the output from this method isn't compatible with the spec, and if you change the source after starting capture, the output capture stream can't accept the new source data due to that incompatibility, so no [`MediaStreamTrack`](../mediastreamtrack)s from the new source `MediaStream` are added to the captured stream, resulting in output that doesn't capture the updated source.
- Switching the source back to a `MediaStream` adds tracks back to the stream and it works again as expected.
- Calling `mozCaptureMediaStream()` on an element with a `MediaStream` source returns a stream that only contains tracks while the element is playing a `MediaStream`.
- If you call `mozCaptureMediaStream()` on a media element with no source media, its compatibility mode will be based on the first source that's added; for example, if it's a `MediaStream`, then the capture stream will only work with MediaStream sources from then on.
- This special behavior will be removed once the non-`MediaStream` source support is brought up to specification and the method is unprefixed. See [bug 1259788, comment 160](https://bugzilla.mozilla.org/show_bug.cgi?id=1259788#c160) for details.

## See also

- [Recording a media element](../mediastream_recording_api/recording_a_media_element)
- [MediaStream Recording API](../mediastream_recording_api)
- [`HTMLCanvasElement.captureStream()`](../htmlcanvaselement/capturestream)
- [`MediaStream`](../mediastream)
- [WebRTC API](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/captureStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/captureStream</a>
