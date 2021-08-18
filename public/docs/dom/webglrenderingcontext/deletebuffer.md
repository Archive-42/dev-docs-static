WebGLRenderingContext.deleteBuffer()
====================================

The `WebGLRenderingContext.deleteBuffer()` method of the [WebGL API](../webgl_api) deletes a given [`WebGLBuffer`](../webglbuffer). This method has no effect if the buffer has already been deleted.

Syntax
------

    void gl.deleteBuffer(buffer);

### Parameters

buffer  
A [`WebGLBuffer`](../webglbuffer) object to delete.

### Return value

None.

Examples
--------

### Deleting a buffer

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var buffer = gl.createBuffer();

    // ...

    gl.deleteBuffer(buffer);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.5">WebGL 1.0<br />
<span class="small">The definition of 'deleteBuffer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glDeleteBuffers.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glDeleteBuffers' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`deleteBuffer`

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

-   [`WebGLRenderingContext.bindBuffer()`](bindbuffer)
-   [`WebGLRenderingContext.createBuffer()`](createbuffer)
-   [`WebGLRenderingContext.isBuffer()`](isbuffer)
-   Other buffers: [`WebGLFramebuffer`](../webglframebuffer), [`WebGLRenderbuffer`](../webglrenderbuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/deleteBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/deleteBuffer</a>
