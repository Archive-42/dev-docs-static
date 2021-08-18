WebGLRenderingContext.createBuffer()
====================================

The `WebGLRenderingContext.createBuffer()` method of the [WebGL API](../webgl_api) creates and initializes a [`WebGLBuffer`](../webglbuffer) storing data such as vertices or colors.

Syntax
------

    WebGLBuffer gl.createBuffer();

### Parameters

None.

### Return value

A [`WebGLBuffer`](../webglbuffer) storing data such as vertices or colors.

Examples
--------

### Creating a buffer

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var buffer = gl.createBuffer();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.5">WebGL 1.0<br />
<span class="small">The definition of 'createBuffer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGenBuffers.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGenBuffers' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`createBuffer`

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
-   [`WebGLRenderingContext.deleteBuffer()`](deletebuffer)
-   [`WebGLRenderingContext.isBuffer()`](isbuffer)
-   Other buffers: [`WebGLFramebuffer`](../webglframebuffer), [`WebGLRenderbuffer`](../webglrenderbuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/createBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/createBuffer</a>
