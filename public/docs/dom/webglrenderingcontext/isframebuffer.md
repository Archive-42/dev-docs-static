WebGLRenderingContext.isFramebuffer()
=====================================

The `WebGLRenderingContext.isFramebuffer()` method of the [WebGL API](../webgl_api) returns `true` if the passed [`WebGLFramebuffer`](../webglframebuffer) is valid and `false` otherwise.

Syntax
------

    GLboolean gl.isFramebuffer(framebuffer);

### Parameters

framebuffer  
A [`WebGLFramebuffer`](../webglframebuffer) to check.

### Return value

A [`GLboolean`](../webgl_api/types) indicating whether or not the frame buffer is valid.

Examples
--------

### Checking a frame buffer

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var framebuffer = gl.createFramebuffer();

    gl.isFramebuffer(framebuffer);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.6">WebGL 1.0<br />
<span class="small">The definition of 'isFramebuffer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glIsFramebuffer.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glIsFramebuffer' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`isFramebuffer`

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

-   [`WebGLRenderingContext.bindFramebuffer()`](bindframebuffer)
-   [`WebGLRenderingContext.createFramebuffer()`](createframebuffer)
-   [`WebGLRenderingContext.deleteFramebuffer()`](deleteframebuffer)
-   Other buffers: [`WebGLBuffer`](../webglbuffer), [`WebGLRenderbuffer`](../webglrenderbuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/isFramebuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/isFramebuffer</a>
