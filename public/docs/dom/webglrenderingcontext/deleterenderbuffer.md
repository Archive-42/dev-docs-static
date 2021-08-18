WebGLRenderingContext.deleteRenderbuffer()
==========================================

The `WebGLRenderingContext.deleteRenderbuffer()` method of the [WebGL API](../webgl_api) deletes a given [`WebGLRenderbuffer`](../webglrenderbuffer) object. This method has no effect if the render buffer has already been deleted.

Syntax
------

    void gl.deleteRenderbuffer(renderbuffer);

### Parameters

renderbuffer  
A [`WebGLRenderbuffer`](../webglrenderbuffer) object to delete.

### Return value

None.

Examples
--------

### Deleting a renderbuffer

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var renderbuffer = gl.createRenderbuffer();

    // ...

    gl.deleteRenderbuffer(renderbuffer);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.7">WebGL 1.0<br />
<span class="small">The definition of 'deleteRenderbuffer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glDeleteRenderbuffers.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glDeleteRenderbuffers' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`deleteRenderbuffer`

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

-   [`WebGLRenderingContext.bindRenderbuffer()`](bindrenderbuffer)
-   [`WebGLRenderingContext.createRenderbuffer()`](createrenderbuffer)
-   [`WebGLRenderingContext.isRenderbuffer()`](isrenderbuffer)
-   Other buffers: [`WebGLBuffer`](../webglbuffer), [`WebGLFramebuffer`](../webglframebuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/deleteRenderbuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/deleteRenderbuffer</a>
