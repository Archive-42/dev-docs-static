WebGLRenderbuffer
=================

The **WebGLRenderbuffer** interface is part of the [WebGL API](webgl_api) and represents a buffer that can contain an image, or can be source or target of an rendering operation.

Description
-----------

The `WebGLRenderbuffer` object does not define any methods or properties of its own and its content is not directly accessible. When working with `WebGLRenderbuffer` objects, the following methods of the [`WebGLRenderingContext`](webglrenderingcontext) are useful:

-   [`WebGLRenderingContext.bindRenderbuffer()`](webglrenderingcontext/bindrenderbuffer)
-   [`WebGLRenderingContext.createRenderbuffer()`](webglrenderingcontext/createrenderbuffer)
-   [`WebGLRenderingContext.deleteRenderbuffer()`](webglrenderingcontext/deleterenderbuffer)
-   [`WebGLRenderingContext.isRenderbuffer()`](webglrenderingcontext/isrenderbuffer)

Examples
--------

### Creating a render buffer

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var buffer = gl.createRenderbuffer();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.7">WebGL 1.0<br />
<span class="small">The definition of 'WebGLRenderbuffer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WebGLRenderbuffer`

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

-   [`WebGLRenderingContext.bindRenderbuffer()`](webglrenderingcontext/bindrenderbuffer)
-   [`WebGLRenderingContext.createRenderbuffer()`](webglrenderingcontext/createrenderbuffer)
-   [`WebGLRenderingContext.deleteRenderbuffer()`](webglrenderingcontext/deleterenderbuffer)
-   [`WebGLRenderingContext.isRenderbuffer()`](webglrenderingcontext/isrenderbuffer)
-   Other buffers: [`WebGLBuffer`](webglbuffer), [`WebGLFramebuffer`](webglframebuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderbuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderbuffer</a>
