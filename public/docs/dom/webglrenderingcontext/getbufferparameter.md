WebGLRenderingContext.getBufferParameter()
==========================================

The `WebGLRenderingContext.getBufferParameter()` method of the [WebGL API](../webgl_api) returns information about the buffer.

Syntax
------

    any gl.getBufferParameter(target, pname);

### Parameters

target  
A [`Glenum`](../webgl_api/types) specifying the target buffer object. Possible values:

-   `gl.ARRAY_BUFFER`: Buffer containing vertex attributes, such as vertex coordinates, texture coordinate data, or vertex color data.
-   `gl.ELEMENT_ARRAY_BUFFER`: Buffer used for element indices.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.COPY_READ_BUFFER`: Buffer for copying from one buffer object to another.
    -   `gl.COPY_WRITE_BUFFER`: Buffer for copying from one buffer object to another.
    -   `gl.TRANSFORM_FEEDBACK_BUFFER`: Buffer for transform feedback operations.
    -   `gl.UNIFORM_BUFFER`: Buffer used for storing uniform blocks.
    -   `gl.PIXEL_PACK_BUFFER`: Buffer used for pixel transfer operations.
    -   `gl.PIXEL_UNPACK_BUFFER`: Buffer used for pixel transfer operations.

pname  
A [`Glenum`](../webgl_api/types) specifying information to query. Possible values:

-   `gl.BUFFER_SIZE`: Returns a [`GLint`](../webgl_api/types) indicating the size of the buffer in bytes.
-   `gl.BUFFER_USAGE`: Returns a [`GLenum`](../webgl_api/types) indicating the usage pattern of the buffer. This is either:
    -   `gl.STATIC_DRAW`,
    -   `gl.DYNAMIC_DRAW`,
    -   `gl.STREAM_DRAW`.
    -   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
        -   `gl.STATIC_READ`,
        -   `gl.DYNAMIC_READ,`
        -   `gl.STREAM_READ`,
        -   `gl.STATIC_COPY`,
        -   `gl.DYNAMIC_COPY,`
        -   `gl.STREAM_COPY`.

### Return value

Depends on the requested information (as specified with `pname`). Either a [`GLint`](../webgl_api/types) or a [`GLenum`](../webgl_api/types).

Examples
--------

    gl.getBufferParameter(gl.ARRAY_BUFFER, gl.BUFFER_SIZE);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.5">WebGL 1.0<br />
<span class="small">The definition of 'getBufferParameter' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetBufferParameteriv.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetBufferParameteriv' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 2 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.3">WebGL 2.0<br />
<span class="small">The definition of 'getBufferParameter' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Updated definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetBufferParameter.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetBufferParameter' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3 API.<br />
<br />
Adds new <code>target</code> buffers:<br />
<code>gl.COPY_READ_BUFFER</code>,<br />
<code>gl.COPY_WRITE_BUFFER</code>,<br />
<code>gl.TRANSFORM_FEEDBACK_BUFFER</code>,<br />
<code>gl.UNIFORM_BUFFER</code>,<br />
<code>gl.PIXEL_PACK_BUFFER</code>,<br />
<code>gl.PIXEL_UNPACK_BUFFER</code><br />
<br />
Adds new <code>usage</code> hints:<br />
<code>gl.STATIC_READ</code>,<br />
<code>gl.DYNAMIC_READ</code>,<br />
<code>gl.STREAM_READ</code>,<br />
<code>gl.STATIC_COPY</code>,<br />
<code>gl.DYNAMIC_COPY</code>,<br />
<code>gl.STREAM_COPY</code>.</td></tr></tbody></table>

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

`getBufferParameter`

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

-   [`WebGLRenderingContext.bindBuffer()`](bindbuffer)
-   [`WebGLRenderingContext.createBuffer()`](createbuffer)
-   [`WebGLRenderingContext.deleteBuffer()`](deletebuffer)
-   [`WebGLRenderingContext.bufferData()`](bufferdata)
-   Other buffers: [`WebGLFramebuffer`](../webglframebuffer), [`WebGLRenderbuffer`](../webglrenderbuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getBufferParameter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getBufferParameter</a>
