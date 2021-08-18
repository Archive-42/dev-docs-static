WebGLRenderingContext.bindBuffer()
==================================

The `WebGLRenderingContext.bindBuffer()` method of the [WebGL API](../webgl_api) binds a given [`WebGLBuffer`](../webglbuffer) to a target.

Syntax
------

    void gl.bindBuffer(target, buffer);

### Parameters

target  
A [`GLenum`](../webgl_api/types) specifying the binding point (target). Possible values:

-   `gl.ARRAY_BUFFER`: Buffer containing vertex attributes, such as vertex coordinates, texture coordinate data, or vertex color data.
-   `gl.ELEMENT_ARRAY_BUFFER`: Buffer used for element indices.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.COPY_READ_BUFFER`: Buffer for copying from one buffer object to another.
    -   `gl.COPY_WRITE_BUFFER`: Buffer for copying from one buffer object to another.
    -   `gl.TRANSFORM_FEEDBACK_BUFFER`: Buffer for transform feedback operations.
    -   `gl.UNIFORM_BUFFER`: Buffer used for storing uniform blocks.
    -   `gl.PIXEL_PACK_BUFFER`: Buffer used for pixel transfer operations.
    -   `gl.PIXEL_UNPACK_BUFFER`: Buffer used for pixel transfer operations.

buffer  
A [`WebGLBuffer`](../webglbuffer) to bind.

### Return value

None.

### Exceptions

Only one target can be bound to a given [`WebGLBuffer`](../webglbuffer). An attempt to bind the buffer to another target will throw an `INVALID_OPERATION` error and the current buffer binding will remain the same.

A [`WebGLBuffer`](../webglbuffer) which has been marked for deletion with [`deleteBuffer`](deletebuffer) cannot be (re-)bound. An attempt to do so will generate an `INVALID_OPERATION` error, and the current binding will remain untouched.

Examples
--------

### Binding a buffer to a target

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var buffer = gl.createBuffer();

    gl.bindBuffer(gl.ARRAY_BUFFER, buffer);

### Getting current bindings

To check the current buffer bindings, query the `ARRAY_BUFFER_BINDING` and `ELEMENT_ARRAY_BUFFER_BINDING` constants.

    gl.getParameter(gl.ARRAY_BUFFER_BINDING);
    gl.getParameter(gl.ELEMENT_ARRAY_BUFFER_BINDING);

Specifications
--------------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.5">WebGL 1.0<br />
<span class="small">The definition of 'bindBuffer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glBindBuffer.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glBindBuffer' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 2 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.1">WebGL 2.0<br />
<span class="small">The definition of 'bindBuffer' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td><p>Updated definition for WebGL 2.</p><p>Adds new <code>target</code> buffers:<br />
<code>gl.COPY_READ_BUFFER</code>,<br />
<code>gl.COPY_WRITE_BUFFER</code>,<br />
<code>gl.TRANSFORM_FEEDBACK_BUFFER</code>,<br />
<code>gl.UNIFORM_BUFFER</code>,<br />
<code>gl.PIXEL_PACK_BUFFER</code>,<br />
<code>gl.PIXEL_UNPACK_BUFFER</code></p></td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glBindBuffer.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glBindBuffer' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3 API.</td></tr></tbody></table>

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

`bindBuffer`

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

-   [`WebGLRenderingContext.createBuffer()`](createbuffer)
-   [`WebGLRenderingContext.deleteBuffer()`](deletebuffer)
-   [`WebGLRenderingContext.isBuffer()`](isbuffer)
-   Other buffers: [`WebGLFramebuffer`](../webglframebuffer), [`WebGLRenderbuffer`](../webglrenderbuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/bindBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/bindBuffer</a>
