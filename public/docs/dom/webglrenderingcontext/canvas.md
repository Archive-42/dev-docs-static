WebGLRenderingContext.canvas
============================

The `WebGLRenderingContext.canvas` property is a read-only reference to the [`HTMLCanvasElement`](../htmlcanvaselement) or [`OffscreenCanvas`](../offscreencanvas) object that is associated with the context. It might be [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) if it is not associated with a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element or an [`OffscreenCanvas`](../offscreencanvas) object.

Syntax
------

    gl.canvas;

### Return value

Either a [`HTMLCanvasElement`](../htmlcanvaselement) or [`OffscreenCanvas`](../offscreencanvas) object or [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null).

Examples
--------

### Canvas element

Given this [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element:

    <canvas id="canvas"></canvas>

You can get back a reference to it from the `WebGLRenderingContext` using the `canvas` property:

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    gl.canvas; // HTMLCanvasElement

### Offscreen canvas

Example using the experimental [`OffscreenCanvas`](../offscreencanvas) object.

    var offscreen = new OffscreenCanvas(256, 256);
    var gl = offscreen.getContext('webgl');
    gl.canvas; // OffscreenCanvas

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#DOM-WebGLRenderingContext-canvas">WebGL 1.0<br />
<span class="small">The definition of 'WebGLRenderingContext.canvas' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`canvas`

9

12

4

11

12

5.1

≤37

25

Yes

12

8

1.5

`OffscreenCanvas`

No

No

44

No

No

No

No

No

No

No

No

No

See also
--------

-   [`CanvasRenderingContext2D.canvas`](../canvasrenderingcontext2d/canvas)
-   [`OffscreenCanvas`](../offscreencanvas)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/canvas" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/canvas</a>
