WEBGL\_draw\_buffers.drawBuffersWEBGL()
=======================================

The `WEBGL_draw_buffers.drawBuffersWEBGL()` method is part of the [WebGL API](../webgl_api) and allows you to define the draw buffers to which all fragment colors are written.

This method is part of the [`WEBGL_draw_buffers`](../webgl_draw_buffers) extension.

**Note:** When using [`WebGL2`](../webgl2renderingcontext), this method is available as [`gl.drawBuffers()`](../webgl2renderingcontext/drawbuffers) by default and the constants are named `gl.COLOR_ATTACHMENT1` etc. without the "WEBGL" suffix.

Syntax
------

    void gl.getExtension('WEBGL_draw_buffers').drawBuffersWEBGL(buffers);

### Parameters

buffers  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLenum`](../webgl_api/types) constants defining drawing buffers. Possible values:

-   `gl.NONE`: The fragment shader is not written to any color buffer.
-   `gl.BACK`: The fragment shader is written to the back color buffer.
-   `ext.COLOR_ATTACHMENT0_WEBGL` The fragment shader is written the *n*th color attachment of the framebuffer.
-   `ext.COLOR_ATTACHMENT1_WEBGL`
-   `ext.COLOR_ATTACHMENT2_WEBGL`
-   `ext.COLOR_ATTACHMENT3_WEBGL`
-   `ext.COLOR_ATTACHMENT4_WEBGL`
-   `ext.COLOR_ATTACHMENT5_WEBGL`
-   `ext.COLOR_ATTACHMENT6_WEBGL`
-   `ext.COLOR_ATTACHMENT7_WEBGL`
-   `ext.COLOR_ATTACHMENT8_WEBGL`
-   `ext.COLOR_ATTACHMENT9_WEBGL`
-   `ext.COLOR_ATTACHMENT10_WEBGL`
-   `ext.COLOR_ATTACHMENT11_WEBGL`
-   `ext.COLOR_ATTACHMENT12_WEBGL`
-   `ext.COLOR_ATTACHMENT13_WEBGL`
-   `ext.COLOR_ATTACHMENT14_WEBGL`
-   `ext.COLOR_ATTACHMENT15_WEBGL`

### Return value

None.

Examples
--------

See [`WEBGL_draw_buffers`](../webgl_draw_buffers) for more context with this example code.

    ext.drawBuffersWEBGL([
      ext.COLOR_ATTACHMENT0_WEBGL, // gl_FragData[0]
      ext.COLOR_ATTACHMENT1_WEBGL, // gl_FragData[1]
      ext.COLOR_ATTACHMENT2_WEBGL, // gl_FragData[2]
      ext.COLOR_ATTACHMENT3_WEBGL  // gl_FragData[3]
    ]);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_draw_buffers/">WEBGL_draw_buffers<br />
<span class="small">The definition of 'WEBGL_draw_buffers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glDrawBuffers.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glDrawBuffers' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`drawBuffersWEBGL`

36

17

28

No

23

9

No

No

?

No

No

No

See also
--------

-   [`WEBGL_draw_buffers`](../webgl_draw_buffers)
-   [`WebGLRenderingContext.getExtension()`](../webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.framebufferRenderbuffer()`](../webglrenderingcontext/framebufferrenderbuffer),
-   [`WebGLRenderingContext.framebufferTexture2D()`](../webglrenderingcontext/framebuffertexture2d),
-   [`WebGLRenderingContext.getFramebufferAttachmentParameter()`](../webglrenderingcontext/getframebufferattachmentparameter)
-   [`WebGLRenderingContext.getParameter()`](../webglrenderingcontext/getparameter)
-   [WebGL deferred shading - Mozilla Hacks blog](https://hacks.mozilla.org/2014/01/webgl-deferred-shading/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_draw_buffers/drawBuffersWEBGL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_draw_buffers/drawBuffersWEBGL</a>
