WebGLRenderingContext.bindFramebuffer()
=======================================

The `WebGLRenderingContext.bindFramebuffer()` method of the [WebGL API](../webgl_api) binds a given [`WebGLFramebuffer`](../webglframebuffer) to a target.

Syntax
------

    void gl.bindFramebuffer(target, framebuffer);

### Parameters

target  
A [`GLenum`](../webgl_api/types) specifying the binding point (target). Possible values:

-   `gl.FRAMEBUFFER`: Collection buffer data storage of color, alpha, depth and stencil buffers used to render an image.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.DRAW_FRAMEBUFFER`: Equivalent to `gl.FRAMEBUFFER`. Used as a destination for drawing, rendering, clearing, and writing operations.
    -   `gl.READ_FRAMEBUFFER`: Used as a source for reading operations.

framebuffer  
A [`WebGLFramebuffer`](../webglframebuffer) object to bind. If `framebuffer` is null, then the canvas (which has no [`WebGLFramebuffer`](../webglframebuffer) object) is bound.

### Return value

None.

### Exceptions

A `gl.INVALID_ENUM` error is thrown if `target` is not `gl.FRAMEBUFFER`, `gl.DRAW_FRAMEBUFFER`, or `gl.READ_FRAMEBUFFER`.

Examples
--------

### Binding a frame buffer

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var framebuffer = gl.createFramebuffer();

    gl.bindFramebuffer(gl.FRAMEBUFFER, framebuffer);

### Getting current bindings

To check the current frame buffer binding, query the `FRAMEBUFFER_BINDING` constant.

    gl.getParameter(gl.FRAMEBUFFER_BINDING);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.6">WebGL 1.0<br />
<span class="small">The definition of 'bindFramebuffer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glBindFramebuffer.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glBindFramebuffer' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.1">WebGL 2.0<br />
<span class="small">The definition of 'bindFrameBuffer' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Updated definition for WebGL 2.<br />
Adds: <code>gl.DRAW_FRAMEBUFFER</code> and <code>gl.READ_FRAMEBUFFER</code></td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glBindFramebuffer.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glBindFramebuffer' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3 API.</td></tr></tbody></table>

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

`bindFramebuffer`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/bindFramebuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/bindFramebuffer</a>
