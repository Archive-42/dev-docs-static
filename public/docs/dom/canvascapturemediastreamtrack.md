# CanvasCaptureMediaStreamTrack

The `CanvasCaptureMediaStreamTrack` interface represents the video track contained in a [`MediaStream`](mediastream) being generated from a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) following a call to [`HTMLCanvasElement.captureStream()`](htmlcanvaselement/capturestream).

Part of the [Media Capture and Streams API](media_streams_api).

## Properties

_This interface inherits the properties of its parent, [`MediaStreamTrack`](mediastreamtrack)._

[`CanvasCaptureMediaStreamTrack.canvas`](canvascapturemediastreamtrack/canvas) <span class="badge inline readonly">Read only </span>  
Returns the [`HTMLCanvasElement`](htmlcanvaselement) object whose surface is captured in real-time.

## Methods

_This interface inherits the methods of its parent, [`MediaStreamTrack`](mediastreamtrack)._

[`CanvasCaptureMediaStreamTrack.requestFrame()`](canvascapturemediastreamtrack/requestframe)  
Manually forces a frame to be captured and sent to the stream. This lets applications that wish to specify the frame capture times directly do so, if they specified a `frameRate` of 0 when calling [`captureStream()`](htmlcanvaselement/capturestream).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-fromelement/#the-canvascapturemediastreamtrack">Media Capture from DOM Elements<br />
<span class="small">The definition of 'CanvasCaptureMediaStreamTrack' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`CanvasCaptureMediaStreamTrack`

51

79

41

No

No

No

51

51

41

No

No

5.0

`canvas`

No

No

41

No

No

No

No

No

41

No

No

No

`requestFrame`

51

79

41

No

No

No

51

51

?

No

No

5.0

## See also

- [`HTMLCanvasElement.captureStream()`](htmlcanvaselement/capturestream) to begin capturing frames from a canvas

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasCaptureMediaStreamTrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasCaptureMediaStreamTrack</a>
