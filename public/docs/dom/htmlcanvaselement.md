# HTMLCanvasElement

The `HTMLCanvasElement` interface provides properties and methods for manipulating the layout and presentation of [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) elements. The `HTMLCanvasElement` interface also inherits the properties and methods of the [`HTMLElement`](htmlelement) interface.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

[`HTMLCanvasElement.height`](htmlcanvaselement/height)  
The [`height`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas#attr-height) HTML attribute of the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element is a positive `integer` reflecting the number of logical pixels (or RGBA values) going down one column of the canvas. When the attribute is not specified, or if it is set to an invalid value, like a negative, the default value of `150` is used. If no \[separate\] CSS height is assigned to the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas), then this value will also be used as the height of the canvas in the length-unit CSS Pixel.

[`HTMLCanvasElement.width`](htmlcanvaselement/width)  
The [`width`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas#attr-width) HTML attribute of the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element is a positive `integer` reflecting the number of logical pixels (or RGBA values) going across one row of the canvas. When the attribute is not specified, or if it is set to an invalid value, like a negative, the default value of `300` is used. If no \[separate\] CSS width is assigned to the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas), then this value will also be used as the width of the canvas in the length-unit CSS Pixel.

[`HTMLCanvasElement.mozOpaque`](htmlcanvaselement/mozopaque) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the [`moz-opaque`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas#attr-moz-opaque) HTML attribute of the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element. It lets the canvas know whether or not translucency will be a factor. If the canvas knows there's no translucency, painting performance can be optimized. This is only supported in Mozilla-based browsers; use the standardized [`canvas.getContext('2d', { alpha: false })`](htmlcanvaselement/getcontext) instead.

<span class="page-not-created">`HTMLCanvasElement.mozPrintCallback`</span><span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Is a `function` that is Initially null. Web content can set this to a JavaScript function that will be called when the canvas is to be redrawn while the page is being printed. When called, the callback is passed a "printState" object that implements the [MozCanvasPrintState](https://searchfox.org/mozilla-central/search?q=interface%20MozCanvasPrintState&path=HTMLCanvasElement.webidl) interface. The callback can get the context to draw to from the printState object and must then call done() on it when finished. The purpose of `mozPrintCallback` is to obtain a higher resolution rendering of the canvas at the resolution of the printer being used. [See this blog post.](https://blog.mozilla.org/labs/2012/09/a-new-way-to-control-printing-output/)

## Methods

_Inherits methods from its parent, [`HTMLElement`](htmlelement)._

[`HTMLCanvasElement.captureStream()`](htmlcanvaselement/capturestream) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a [`CanvasCaptureMediaStreamTrack`](canvascapturemediastreamtrack) that is a real-time video capture of the surface of the canvas.

[`HTMLCanvasElement.getContext()`](htmlcanvaselement/getcontext)  
Returns a drawing context on the canvas, or null if the context ID is not supported. A drawing context lets you draw on the canvas. Calling getContext with `"2d"` returns a [`CanvasRenderingContext2D`](canvasrenderingcontext2d) object, whereas calling it with `"webgl"` (or `"experimental-webgl"`) returns a [`WebGLRenderingContext`](webglrenderingcontext) object. This context is only available on browsers that implement [WebGL](webgl_api).

[`HTMLCanvasElement.toDataURL()`](htmlcanvaselement/todataurl)  
Returns a data-URL containing a representation of the image in the format specified by the `type` parameter (defaults to `png`). The returned image is in a resolution of 96dpi.

[`HTMLCanvasElement.toBlob()`](htmlcanvaselement/toblob)  
Creates a [`Blob`](blob) object representing the image contained in the canvas; this file may be cached on the disk or stored in memory at the discretion of the user agent.

[`HTMLCanvasElement.transferControlToOffscreen()`](htmlcanvaselement/transfercontroltooffscreen) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Transfers control to an [`OffscreenCanvas`](offscreencanvas) object, either on the main thread or on a worker.

### Obsolete methods

[`HTMLCanvasElement.mozGetAsFile()`](htmlcanvaselement/mozgetasfile) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns a [`File`](file) object representing the image contained in the canvas; this file is a memory-based file, with the specified `name`. If `type` is not specified, the image type is `image/png`.

## Events

Listen to these events using `addEventListener()`.

`webglcontextcreationerror`  
Fired if the user agent is unable to create a `WebGLRenderingContext` or `WebGL2RenderingContext` context.

`webglcontextlost`  
Fired if the user agent detects that the drawing buffer associated with a `WebGLRenderingContext` or `WebGL2RenderingContext` object has been lost.

`webglcontextrestored`  
Fired if the user agent restores the drawing buffer for a `WebGLRenderingContext` or `WebGL2RenderingContext` object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlcanvaselement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLCanvasElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Primary definition of <code>HTMLCanvasElement</code>.</td></tr><tr class="even"><td><a href="https://w3c.github.io/mediacapture-fromelement/#html-canvas-element-media-capture-extensions">Media Capture from DOM Elements<br />
<span class="small">The definition of 'HTMLCanvasElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the method <code>captureStream()</code>.</td></tr></tbody></table>

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

`HTMLCanvasElement`

1

12

1.5

9

9

Opera Mini 5.0 and later has partial support.

3

1

18

4

10.1

Opera Mini 5.0 and later has partial support.

1

1.0

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

`getContext`

1

12

1.5

9

9

3

1

18

4

10.1

1

1.0

`height`

1

12

1.5

9

9

3

1

18

4

10.1

1

1.0

`mozFetchAsStream`

No

No

13-23

No

No

No

No

No

14-23

No

No

No

`mozGetAsFile`

No

No

4-74

`mozGetAsFile()` was deprecated in Firefox 26 (in 2013) and was removed entirely in Firefox 74.

No

No

No

No

No

4

No

No

No

`mozOpaque`

No

No

3.5

No

No

No

No

No

4

No

No

No

`toBlob`

50

79

12-79

18

10

37

11

50

50

18

37

11

5.0

`toDataURL`

1

12

2

9

9

4

1

18

4

10.1

3

1.0

`transferControlToOffscreen`

69

79

44

No

56

No

No

69

44

48

No

10.0

`webglcontextcreationerror_event`

9

12

49

11

12

5.1

≤37

25

49

12

8

1.5

`webglcontextlost_event`

9

12

4

11

12

5.1

≤37

25

4

12

8

1.5

`webglcontextrestored_event`

9

12

4

11

12

5.1

≤37

25

4

12

8

1.5

`width`

1

12

1.5

9

9

3

1

18

4

10.1

1

1.0

## See also

- HTML element implementing this interface: [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement</a>
