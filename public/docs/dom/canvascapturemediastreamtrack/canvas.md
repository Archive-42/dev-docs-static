# CanvasCaptureMediaStreamTrack.canvas

The [`CanvasCaptureMediaStreamTrack`](../canvascapturemediastreamtrack) `canvas` read-only property returns the [`HTMLCanvasElement`](../htmlcanvaselement) from which frames are being captured.

## Syntax

    var elt = stream.canvas;

### Value

An `HTMLCanvasElement` indicating the canvas which is the source of the frames being captured.

## Example

    // Find the canvas element to capture
    var canvasElt = document.getElementsByTagName("canvas")[0];

    // Get the stream
    var stream = canvasElt.captureStream(25); // 25 FPS

    // Do things to the stream
    ...

    // Obtain the canvas associated with the stream
    var canvas = stream.canvas;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-fromelement/#dom-canvascapturemediastreamtrack-canvas">Media Capture from DOM Elements<br />
<span class="small">The definition of 'CanvasCaptureMediaStreamTrack.canvas' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

## See also

- [`HTMLCanvasElement.captureStream()`](../htmlcanvaselement/capturestream) to create a stream to capture a given canvas element.
- [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasCaptureMediaStreamTrack/canvas" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasCaptureMediaStreamTrack/canvas</a>
