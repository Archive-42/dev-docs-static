WebGLRenderingContext.createRenderbuffer()
==========================================

The `WebGLRenderingContext.createRenderbuffer()` method of the [WebGL API](../webgl_api) creates and initializes a [`WebGLRenderbuffer`](../webglrenderbuffer) object.

Syntax
------

    WebGLRenderbuffer gl.createRenderbuffer();

### Parameters

None.

### Return value

A [`WebGLRenderbuffer`](../webglrenderbuffer) object that stores data such an image, or can be source or target of an rendering operation.

Examples
--------

### Creating a render buffer

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var renderBuffer = gl.createRenderbuffer();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.7">WebGL 1.0<br />
<span class="small">The definition of 'createRenderbuffer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGenRenderbuffers.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGenRenderbuffers' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`createRenderbuffer`

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
-   [`WebGLRenderingContext.deleteRenderbuffer()`](deleterenderbuffer)
-   [`WebGLRenderingContext.isRenderbuffer()`](isrenderbuffer)
-   Other buffers: [`WebGLBuffer`](../webglbuffer), [`WebGLFramebuffer`](../webglframebuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/createRenderbuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/createRenderbuffer</a>
