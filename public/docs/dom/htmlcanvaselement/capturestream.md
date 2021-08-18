HTMLCanvasElement.captureStream()
=================================

The [`HTMLCanvasElement`](../htmlcanvaselement) `captureStream()` method returns a [`MediaStream`](../mediastream) which includes a [`CanvasCaptureMediaStreamTrack`](../canvascapturemediastreamtrack) containing a real-time video capture of the canvas's contents.

Syntax
------

    MediaStream = canvas.captureStream(frameRate);

### Parameters

 `frameRate` <span class="badge inline optional">Optional</span>   
A double-precision floating-point value that indicates the rate of capture of each frame. If not set, a new frame will be captured each time the canvas changes; if set to `0`, frames will not be captured automatically; instead, they will only be captured when the returned track's [`requestFrame()`](../canvascapturemediastreamtrack/requestframe) method is called.

### Return value

A reference to a [`MediaStream`](../mediastream) object, which has a single [`CanvasCaptureMediaStreamTrack`](../canvascapturemediastreamtrack) in it.

### Exceptions

`NotSupportedError`  
The value of `frameRate` is negative.

Example
-------

    // Find the canvas element to capture
    var canvasElt = document.querySelector('canvas');

    // Get the stream
    var stream = canvasElt.captureStream(25); // 25 FPS

    // Do things to the stream
    // E.g. Send it to another computer using an RTCPeerConnection
    //      pc is an RTCPeerConnection created elsewhere
    pc.addStream(stream);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-fromelement/#dom-htmlcanvaselement-capturestream">Media Capture from DOM Elements<br />
<span class="small">The definition of 'HTMLCanvasElement.captureStream()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

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

51

79

43

No

36

11

51

51

43

36

11

5.0

See also
--------

-   [`HTMLMediaElement.captureStream()`](../htmlmediaelement/capturestream), which allows capturing a stream from a media element.
-   [`MediaStream`](../mediastream)
-   <span class="page-not-created">`Media Capture and Streams API`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/captureStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/captureStream</a>
