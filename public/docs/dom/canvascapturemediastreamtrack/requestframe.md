# CanvasCaptureMediaStreamTrack.requestFrame()

The [`CanvasCaptureMediaStreamTrack`](../canvascapturemediastreamtrack) method `requestFrame()` requests that a frame be captured from the canvas and sent to the stream. Applications that need to carefully control the timing of rendering and frame capture can use `requestFrame()` to directly specify when it's time to capture a frame.

To prevent automatic capture of frames, so that frames are only captured when `requestFrame()` is called, specify a value of 0 for the [`captureStream()`](../htmlcanvaselement/capturestream) method when creating the stream.

## Syntax

    stream.requestFrame();

### Return value

`undefined`

## Usage notes

There is currently an issue flagged in the specification pointing out that at this time, no exceptions are being thrown if the canvas isn't origin-clean. This may change in the future, so it would be wise to plan ahead and watch for exceptions such as `SecurityError` (although the specific error that might be thrown is not mentioned in the spec, this is a likely candidate).

## Example

    // Find the canvas element to capture
    var canvasElt = document.getElementsByTagName("canvas")[0];

    // Get the stream
    var stream = canvasElt.captureStream(25); // 25 FPS

    // Send the current state of the canvas as a frame to the stream
    stream.getVideoTracks()[0].requestFrame();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-fromelement/#dom-canvascapturemediastreamtrack-requestframe">Media Capture from DOM Elements<br />
<span class="small">The definition of 'CanvasCaptureMediaStream.requestFrame()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

- [`CanvasCaptureMediaStreamTrack`](../canvascapturemediastreamtrack), the interface it belongs to.
- [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasCaptureMediaStreamTrack/requestFrame" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasCaptureMediaStreamTrack/requestFrame</a>
