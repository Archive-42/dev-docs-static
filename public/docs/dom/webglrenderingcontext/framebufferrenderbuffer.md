WebGLRenderingContext.framebufferRenderbuffer()
===============================================

The `WebGLRenderingContext.framebufferRenderbuffer()` method of the [WebGL API](../webgl_api) attaches a [`WebGLRenderbuffer`](../webglrenderbuffer) object to a [`WebGLFramebuffer`](../webglframebuffer) object.

Syntax
------

    void gl.framebufferRenderbuffer(target, attachment, renderbuffertarget, renderbuffer);

### Parameters

target  
A [`GLenum`](../webgl_api/types) specifying the binding point (target) for the framebuffer. Possible values:

-   `gl.FRAMEBUFFER`: Collection buffer data storage of color, alpha, depth and stencil buffers used to render an image.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.DRAW_FRAMEBUFFER`: Equivalent to `gl.FRAMEBUFFER`. Used as a destination for drawing, rendering, clearing, and writing operations.
    -   `gl.READ_FRAMEBUFFER`: Used as a source for reading operations.

attachment  
A [`GLenum`](../webgl_api/types) specifying the attachment point for the render buffer. Possible values:

-   `gl.COLOR_ATTACHMENT0`: color buffer.
-   `gl.DEPTH_ATTACHMENT`: depth buffer.
-   `gl.DEPTH_STENCIL_ATTACHMENT`: depth and stencil buffer.
-   `gl.STENCIL_ATTACHMENT`: stencil buffer.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.COLOR_ATTACHMENT1      gl.COLOR_ATTACHMENT2      gl.COLOR_ATTACHMENT3      gl.COLOR_ATTACHMENT4      gl.COLOR_ATTACHMENT5      gl.COLOR_ATTACHMENT6      gl.COLOR_ATTACHMENT7      gl.COLOR_ATTACHMENT8      gl.COLOR_ATTACHMENT9      gl.COLOR_ATTACHMENT10      gl.COLOR_ATTACHMENT11      gl.COLOR_ATTACHMENT12      gl.COLOR_ATTACHMENT13      gl.COLOR_ATTACHMENT14      gl.COLOR_ATTACHMENT15`
-   When using the [`WEBGL_draw_buffers`](../webgl_draw_buffers) extension:
    -   `ext.COLOR_ATTACHMENT0_WEBGL` (same as `gl.COLOR_ATTACHMENT0`)  
        `ext.COLOR_ATTACHMENT1_WEBGL      ext.COLOR_ATTACHMENT2_WEBGL      ext.COLOR_ATTACHMENT3_WEBGL      ext.COLOR_ATTACHMENT4_WEBGL      ext.COLOR_ATTACHMENT5_WEBGL      ext.COLOR_ATTACHMENT6_WEBGL      ext.COLOR_ATTACHMENT7_WEBGL      ext.COLOR_ATTACHMENT8_WEBGL      ext.COLOR_ATTACHMENT9_WEBGL      ext.COLOR_ATTACHMENT10_WEBGL      ext.COLOR_ATTACHMENT11_WEBGL      ext.COLOR_ATTACHMENT12_WEBGL      ext.COLOR_ATTACHMENT13_WEBGL      ext.COLOR_ATTACHMENT14_WEBGL      ext.COLOR_ATTACHMENT15_WEBGL`

renderbuffertarget  
A [`GLenum`](../webgl_api/types) specifying the binding point (target) for the render buffer. Possible values:

-   `gl.RENDERBUFFER`: Buffer data storage for single images in a renderable internal format.

renderbuffer  
A [`WebGLRenderbuffer`](../webglrenderbuffer) object to attach.

### Return value

None.

### Exceptions

-   A `gl.INVALID_ENUM` error is thrown if `target` is not `gl.FRAMEBUFFER`, `gl.DRAW_FRAMEBUFFER`, or `gl.READ_FRAMEBUFFER`.
-   A `gl.INVALID_ENUM` error is thrown if `renderbuffertarget` is not `gl.RENDERBUFFER`.
-   A `gl.INVALID_ENUM` error is thrown if `attachment` is not one of the allowed enums.

Examples
--------

    gl.framebufferRenderbuffer(gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.RENDERBUFFER, renderbuffer);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.6">WebGL 1.0<br />
<span class="small">The definition of 'framebufferRenderbuffer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glFramebufferRenderbuffer.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glFramebufferRenderbuffer' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glFramebufferRenderbuffer.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glFramebufferRenderbuffer' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3 API.</td></tr></tbody></table>

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

`framebufferRenderbuffer`

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

`WebGL2`

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

-   [`WebGLRenderingContext.createFramebuffer()`](createframebuffer)
-   [`WebGLRenderingContext.deleteFramebuffer()`](deleteframebuffer)
-   [`WebGLRenderingContext.isFramebuffer()`](isframebuffer)
-   Other buffers: [`WebGLBuffer`](../webglbuffer), [`WebGLRenderbuffer`](../webglrenderbuffer)
-   [`WEBGL_draw_buffers`](../webgl_draw_buffers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/framebufferRenderbuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/framebufferRenderbuffer</a>
