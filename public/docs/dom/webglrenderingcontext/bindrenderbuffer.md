WebGLRenderingContext.bindRenderbuffer()
========================================

The `WebGLRenderingContext.bindRenderbuffer()` method of the [WebGL API](../webgl_api) binds a given [`WebGLRenderbuffer`](../webglrenderbuffer) to a target, which must be `gl.RENDERBUFFER`.

Syntax
------

    void gl.bindRenderbuffer(target, renderbuffer);

### Parameters

target  
A [`GLenum`](../webgl_api/types) specifying the binding point (target). Possible values:

-   `gl.RENDERBUFFER`: Buffer data storage for single images in a renderable internal format.

renderbuffer  
A [`WebGLRenderbuffer`](../webglrenderbuffer) object to bind.

### Return value

None.

### Exceptions

A `gl.INVALID_ENUM` error is thrown if `target` is not `gl.RENDERBUFFER`.

Examples
--------

### Binding a renderbuffer

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var renderbuffer = gl.createRenderbuffer();

    gl.bindRenderbuffer(gl.RENDERBUFFER, renderbuffer);

### Getting current bindings

To check the current renderbuffer binding, query the `RENDERBUFFER_BINDING` constant.

    gl.getParameter(gl.RENDERBUFFER_BINDING);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.7">WebGL 1.0<br />
<span class="small">The definition of 'bindRenderbuffer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glBindRenderbuffer.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glBindRenderbuffer' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`bindRenderbuffer`

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

-   [`WebGLRenderingContext.createRenderbuffer()`](createrenderbuffer)
-   [`WebGLRenderingContext.deleteRenderbuffer()`](deleterenderbuffer)
-   [`WebGLRenderingContext.isRenderbuffer()`](isrenderbuffer)
-   Other buffers: [`WebGLBuffer`](../webglbuffer), [`WebGLFramebuffer`](../webglframebuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/bindRenderbuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/bindRenderbuffer</a>
