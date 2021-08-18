WebGLRenderingContext.checkFramebufferStatus()
==============================================

The `WebGLRenderingContext.checkFramebufferStatus()` method of the [WebGL API](../webgl_api) returns the completeness status of the [`WebGLFramebuffer`](../webglframebuffer) object.

Syntax
------

    GLenum gl.checkFramebufferStatus(target);

### Parameters

target  
A [`GLenum`](../webgl_api/types) specifying the binding point (target). Possible values:

-   `gl.FRAMEBUFFER`: Collection buffer data storage of color, alpha, depth and stencil buffers used to render an image.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.DRAW_FRAMEBUFFER`: Equivalent to `gl.FRAMEBUFFER`. Used as a destination for drawing, rendering, clearing, and writing operations.
    -   `gl.READ_FRAMEBUFFER`: Used as a source for reading operations.

### Return value

A [`GLenum`](../webgl_api/types) indicating the completeness status of the framebuffer or `0` if an error occurs. Possible enum return values:

-   `gl.FRAMEBUFFER_COMPLETE`: The framebuffer is ready to display.
-   `gl.FRAMEBUFFER_INCOMPLETE_ATTACHMENT`: The attachment types are mismatched or not all framebuffer attachment points are framebuffer attachment complete.
-   `gl.FRAMEBUFFER_INCOMPLETE_MISSING_ATTACHMENT`: There is no attachment.
-   `gl.FRAMEBUFFER_INCOMPLETE_DIMENSIONS`: Height and width of the attachment are not the same.
-   `gl.FRAMEBUFFER_UNSUPPORTED`: The format of the attachment is not supported or if depth and stencil attachments are not the same renderbuffer.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values can be returned additionally:
    -   `gl.FRAMEBUFFER_INCOMPLETE_MULTISAMPLE`: The values of `gl.RENDERBUFFER_SAMPLES` are different among attached renderbuffers, or are non-zero if the attached images are a mix of renderbuffers and textures.
-   When using the [`OVR_multiview2`](../ovr_multiview2) extension, the following value can be returned additionally:
    -   `ext.FRAMEBUFFER_INCOMPLETE_VIEW_TARGETS_OVR`: If `baseViewIndex` is not the same for all framebuffer attachment points where the value of `FRAMEBUFFER_ATTACHMENT_OBJECT_TYPE` is not `NONE`, the framebuffer is considered incomplete.

Examples
--------

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var framebuffer = gl.createFramebuffer();

    // ...

    gl.checkFramebufferStatus(gl.FRAMEBUFFER);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.6">WebGL 1.0<br />
<span class="small">The definition of 'checkFramebufferStatus' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glCheckFramebufferStatus.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glCheckFramebufferStatus' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.4">WebGL 2.0<br />
<span class="small">The definition of 'checkFramebufferStatus' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Updated definition for WebGL 2.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glCheckFramebufferStatus.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glCheckFramebufferStatus' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3 API.</td></tr></tbody></table>

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

`checkFramebufferStatus`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/checkFramebufferStatus" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/checkFramebufferStatus</a>
