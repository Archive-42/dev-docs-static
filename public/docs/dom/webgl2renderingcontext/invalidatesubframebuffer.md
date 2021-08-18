WebGL2RenderingContext.invalidateSubFramebuffer()
=================================================

The `WebGL2RenderingContext.invalidateSubFramebuffer()` method of the [WebGL 2 API](../webgl_api) invalidates portions of the contents of attachments in a framebuffer.

Syntax
------

    void gl.invalidateSubFramebuffer(target, attachments, x, y, width, height);

### Parameters

`target`  
A [`GLenum`](../webgl_api/types) specifying the binding point (target). Possible values:

-   `gl.FRAMEBUFFER`: Collection buffer data storage of color, alpha, depth and stencil buffers used to render an image.
-   `gl.DRAW_FRAMEBUFFER`: Equivalent to `gl.FRAMEBUFFER`.
-   `gl.READ_FRAMEBUFFER`: Used as a source for reading operations.

`attachments`  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLenum`](../webgl_api/types) specifying the attachment points to invalidate. Possible values:

-   `gl.COLOR_ATTACHMENT{0-15}`: Invalidates one of the framebuffer's color buffers.
-   `gl.DEPTH_ATTACHMENT`: Invalidates the framebuffer's depth buffer.
-   `gl.STENCIL_ATTACHMENT`: Invalidates the framebuffer's stencil buffer.
-   `gl.DEPTH_STENCIL_ATTACHMENT`: Invalidates both the framebuffer's depth and stencil buffer.

`x`  
A [`GLint`](../webgl_api/types) specifying the left origin of the pixel rectangle to invalidate.

`y`  
A [`GLint`](../webgl_api/types) specifying the bottom origin of the pixel rectangle to invalidate.

`width`  
A [`GLsizei`](../webgl_api/types) specifying the width of the pixel rectangle to invalidate.

`height`  
A [`GLsizei`](../webgl_api/types) specifying the height of the pixel rectangle to invalidate.

### Return value

None.

Examples
--------

    gl.invalidateSubFramebuffer(gl.READ_FRAMEBUFFER,
                                [gl.COLOR_ATTACHMENT0, gl.COLOR_ATTACHMENT1],
                                0, 0, 256, 256);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.4">WebGL 2.0<br />
<span class="small">The definition of 'invalidateSubFramebuffer' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glInvalidateSubFramebuffer.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glInvalidateSubFramebuffer' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`invalidateSubFramebuffer`

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

-   [`WebGL2RenderingContext.invalidateFramebuffer()`](invalidateframebuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/invalidateSubFramebuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/invalidateSubFramebuffer</a>
