WebGL2RenderingContext.blitFramebuffer()
========================================

The `WebGL2RenderingContext.blitFramebuffer()` method of the [WebGL 2 API](../webgl_api) transfers a block of pixels from the read framebuffer to the draw framebuffer. Read and draw framebuffers are bound using [`WebGLRenderingContext.bindFramebuffer()`](../webglrenderingcontext/bindframebuffer).

Syntax
------

    void gl.blitFramebuffer(srcX0, srcY0, srcX1, srcY1,
                            dstX0, dstY0, dstX1, dstY1,
                            mask, filter);

### Parameters

`srcX0, srcY0, srcX1, srcY1`  
A [`GLint`](../webgl_api/types) specifying the bounds of the source rectangle.

`dstX0, dstY0, dstX1, dstY1`  
A [`GLint`](../webgl_api/types) specifying the bounds of the destination rectangle.

`mask`  
A [`GLbitfield`](../webgl_api/types) specifying a bitwise OR mask indicating which buffers are to be copied. Possible values:

-   `gl.COLOR_BUFFER_BIT`
-   `gl.DEPTH_BUFFER_BIT`
-   `gl.STENCIL_BUFFER_BIT`

`filter`  
A [`GLenum`](../webgl_api/types) specifying the interpolation to be applied if the image is stretched. Possible values:

-   `gl.NEAREST`
-   `gl.LINEAR`

### Return value

None.

Examples
--------

    gl.blitFramebuffer(0, 0, canvas.width, canvas.height,
                       0, 0, canvas.width, canvas.height,
                       gl.COLOR_BUFFER_BIT, gl.NEAREST);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.4">WebGL 2.0<br />
<span class="small">The definition of 'blitFramebuffer' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glBlitFramebuffer.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glBlitFramebuffer' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`blitFramebuffer`

56

79

51

No

43

No

58

58

51

43

No

7.0

See also
--------

-   [`WebGLRenderingContext.bindFramebuffer()`](../webglrenderingcontext/bindframebuffer)
-   [`WebGLRenderingContext.getRenderbufferParameter()`](../webglrenderingcontext/getrenderbufferparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/blitFramebuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/blitFramebuffer</a>
