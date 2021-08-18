WebGLRenderingContext.deleteFramebuffer()
=========================================

The `WebGLRenderingContext.deleteFramebuffer()` method of the [WebGL API](../webgl_api) deletes a given [`WebGLFramebuffer`](../webglframebuffer) object. This method has no effect if the frame buffer has already been deleted.

Syntax
------

    void gl.deleteFramebuffer(framebuffer);

### Parameters

framebuffer  
A [`WebGLFramebuffer`](../webglframebuffer) object to delete.

### Return value

None.

Examples
--------

### Deleting a frame buffer

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var framebuffer = gl.createFramebuffer();

    // ...

    gl.deleteFramebuffer(framebuffer);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.6">WebGL 1.0<br />
<span class="small">The definition of 'deleteFramebuffer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glDeleteFramebuffers.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glDeleteFramebuffers' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`deleteFramebuffer`

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
-   [`WebGLRenderingContext.isFramebuffer()`](isframebuffer)
-   Other buffers: [`WebGLBuffer`](../webglbuffer), [`WebGLRenderbuffer`](../webglrenderbuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/deleteFramebuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/deleteFramebuffer</a>
