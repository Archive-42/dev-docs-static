WebGL2RenderingContext.framebufferTextureLayer()
================================================

The `WebGL2RenderingContext.framebufferTextureLayer()` method of the [WebGL 2 API](../webgl_api) attaches a single layer of a texture to a framebuffer.

This method is similar to [`WebGLRenderingContext.framebufferTexture2D()`](../webglrenderingcontext/framebuffertexture2d), but only a given single layer of the texture level is attached to the attachment point.

Syntax
------

    void gl.framebufferTextureLayer(target, attachment, texture, level, layer);

### Parameters

`target`  
A [`GLenum`](../webgl_api/types) specifying the binding point (target). Possible values:

-   `gl.FRAMEBUFFER`: Collection buffer data storage of color, alpha, depth and stencil buffers used to render an image.
-   `gl.DRAW_FRAMEBUFFER`: Equivalent to `gl.FRAMEBUFFER`.
-   `gl.READ_FRAMEBUFFER`: Used as a source for reading operations.

`attachment`  
A [`GLenum`](../webgl_api/types) specifying the attachment point for the `texture`. Possible values:

-   `gl.COLOR_ATTACHMENT{0-15}`: Attaches the texture to one of the framebuffer's color buffers.
-   `gl.DEPTH_ATTACHMENT`: Attaches the texture to the framebuffer's depth buffer.
-   `gl.STENCIL_ATTACHMENT`: Attaches the texture to the framebuffer's stencil buffer.
-   `gl.DEPTH_STENCIL_ATTACHMENT`: depth and stencil buffer.

`texture`  
A [`WebGLTexture`](../webgltexture) object whose image to attach.

`level`  
A [`GLint`](../webgl_api/types) specifying the mipmap level of the texture image to attach.

`layer`  
A [`GLint`](../webgl_api/types) specifying the layer of the texture image to attach.

### Return value

None.

Examples
--------

    gl.framebufferTextureLayer(gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0,
                               texture, 0, 8);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.4">WebGL 2.0<br />
<span class="small">The definition of 'framebufferTextureLayer' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glFramebufferTextureLayer.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glFramebufferTextureLayer' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`framebufferTextureLayer`

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

-   [`WebGLRenderingContext.framebufferTexture2D()`](../webglrenderingcontext/framebuffertexture2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/framebufferTextureLayer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/framebufferTextureLayer</a>
