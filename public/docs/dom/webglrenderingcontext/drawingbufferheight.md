WebGLRenderingContext.drawingBufferHeight
=========================================

The read-only `WebGLRenderingContext.drawingBufferHeight` property represents the actual height of the current drawing buffer. It should match the `height` attribute of the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element associated with this context, but might differ if the implementation is not able to provide the requested height.

Syntax
------

    gl.drawingBufferHeight;

Examples
--------

Given this [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element:

    <canvas id="canvas"></canvas>

You can get the height of the drawing buffer with the following lines:

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    gl.drawingBufferHeight; // 150

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#DOM-WebGLRenderingContext-drawingBufferHeight">WebGL 1.0<br />
<span class="small">The definition of 'WebGLRenderingContext.drawingBufferHeight' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`drawingBufferHeight`

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

See also
--------

-   [`WebGLRenderingContext.drawingBufferWidth`](drawingbufferwidth)
-   [`WebGLRenderingContext.viewport()`](viewport)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/drawingBufferHeight" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/drawingBufferHeight</a>
