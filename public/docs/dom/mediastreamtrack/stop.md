# MediaStreamTrack.stop()

The `MediaStreamTrack.stop()` method stops the track.

## Syntax

    track.stop()

## Description

Calling `stop()` tells the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) that the track's source—whatever that source may be, including files, network streams, or a local camera or microphone—is no longer needed by the [`MediaStreamTrack`](../mediastreamtrack). Since multiple tracks may use the same source (for example, if two tabs are using the device's microphone), the source itself isn't necessarily immediately stopped. It is instead disassociated from the track and the track object is stopped. Once no media tracks are using the source, the source may actually be completely stopped.

Immediately after calling `stop()`, the [`readyState`](readystate) property is set to `ended`.

## Examples

### Stopping a video stream

In this example, we see a function which stops a streamed video by calling `stop()` on every track on a given [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video).

    function stopStreamedVideo(videoElem) {
      const stream = videoElem.srcObject;
      const tracks = stream.getTracks();

      tracks.forEach(function(track) {
        track.stop();
      });

      videoElem.srcObject = null;
    }

This works by obtaining the video element's stream from its [`srcObject`](../htmlmediaelement/srcobject) property. Then the stream's track list is obtained by calling its [`getTracks()`](../mediastream/gettracks) method. From there, all that remains to do is to iterate over the track list using [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) and calling each track's `stop()` method.

Finally, `srcObject` is set to `null` to sever the link to the [`MediaStream`](../mediastream) object so it can be released.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamtrack-stop">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStreamTrack.stop()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`stop`

61

12

34

No

45

11

61

61

34

43

11

8.0

## See also

- [`MediaStreamTrack`](../mediastreamtrack), the interface it belongs to.
- [`MediaStreamTrack.readyState`](readystate)
- `ended`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/stop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/stop</a>
