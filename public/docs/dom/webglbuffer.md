WebGLBuffer
===========

The **WebGLBuffer** interface is part of the [WebGL API](webgl_api) and represents an opaque buffer object storing data such as vertices or colors.

Description
-----------

The `WebGLBuffer` object does not define any methods or properties of its own and its content is not directly accessible. When working with `WebGLBuffer` objects, the following methods of the [`WebGLRenderingContext`](webglrenderingcontext) are useful:

-   [`WebGLRenderingContext.bindBuffer()`](webglrenderingcontext/bindbuffer)
-   [`WebGLRenderingContext.createBuffer()`](webglrenderingcontext/createbuffer)
-   [`WebGLRenderingContext.deleteBuffer()`](webglrenderingcontext/deletebuffer)
-   [`WebGLRenderingContext.isBuffer()`](webglrenderingcontext/isbuffer)

Examples
--------

### Creating a buffer

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var buffer = gl.createBuffer();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.4">WebGL 1.0<br />
<span class="small">The definition of 'WebGLBuffer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WebGLBuffer`

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

`worker_support`

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

-   [`WebGLRenderingContext.bindBuffer()`](webglrenderingcontext/bindbuffer)
-   [`WebGLRenderingContext.createBuffer()`](webglrenderingcontext/createbuffer)
-   [`WebGLRenderingContext.deleteBuffer()`](webglrenderingcontext/deletebuffer)
-   [`WebGLRenderingContext.isBuffer()`](webglrenderingcontext/isbuffer)
-   Other buffers: [`WebGLFramebuffer`](webglframebuffer), [`WebGLRenderbuffer`](webglrenderbuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLBuffer</a>
