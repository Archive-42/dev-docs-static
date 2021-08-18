WebGLRenderingContext.bufferData()
==================================

The `WebGLRenderingContext.bufferData()` method of the [WebGL API](../webgl_api) initializes and creates the buffer object's data store.

Syntax
------

    // WebGL1:
    void gl.bufferData(target, size, usage);
    void gl.bufferData(target, ArrayBuffer? srcData, usage);
    void gl.bufferData(target, ArrayBufferView srcData, usage);

    // WebGL2:
    void gl.bufferData(target, ArrayBufferView srcData, usage, srcOffset, length);

### Parameters

`target`  
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

`size`  
A [`GLsizeiptr`](../webgl_api/types) setting the size in bytes of the buffer object's data store.

 `srcData` <span class="badge inline optional">Optional</span>   
An [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), [`SharedArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer) or one of the [`ArrayBufferView`](../arraybufferview) typed array types that will be copied into the data store. If `null`, a data store is still created, but the content is uninitialized and undefined.

`usage`  
A [`GLenum`](../webgl_api/types) specifying the intended usage pattern of the data store for optimization purposes. Possible values:

-   `gl.STATIC_DRAW`: The contents are intended to be specified once by the application, and used many times as the source for WebGL drawing and image specification commands.
-   `gl.DYNAMIC_DRAW`: The contents are intended to be respecified repeatedly by the application, and used many times as the source for WebGL drawing and image specification commands.
-   `gl.STREAM_DRAW`: The contents are intended to be specified once by the application, and used at most a few times as the source for WebGL drawing and image specification commands.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.STATIC_READ`: The contents are intended to be specified once by reading data from WebGL, and queried many times by the application.
    -   `gl.DYNAMIC_READ`: The contents are intended to be respecified repeatedly by reading data from WebGL, and queried many times by the application.
    -   `gl.STREAM_READ`: The contents are intended to be specified once by reading data from WebGL, and queried at most a few times by the application
    -   `gl.STATIC_COPY`: The contents are intended to be specified once by reading data from WebGL, and used many times as the source for WebGL drawing and image specification commands.
    -   `gl.DYNAMIC_COPY`: The contents are intended to be respecified repeatedly by reading data from WebGL, and used many times as the source for WebGL drawing and image specification commands.
    -   `gl.STREAM_COPY`: The contents are intended to be specified once by reading data from WebGL, and used at most a few times as the source for WebGL drawing and image specification commands.

`srcOffset`  
A [`GLuint`](../webgl_api/types) specifying the element index offset where to start reading the buffer.

 `length` <span class="badge inline optional">Optional</span>   
A [`GLuint`](../webgl_api/types) defaulting to 0.

### Return value

None.

### Exceptions

-   A `gl.OUT_OF_MEMORY` error is thrown if the context is unable to create a data store with the given `size`.
-   A `gl.INVALID_VALUE` error is thrown if `size` is negative.
-   A `gl.INVALID_ENUM` error is thrown if `target` or `usage` are not one of the allowed enums.

Examples
--------

### Using bufferData

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var buffer = gl.createBuffer();
    gl.bindBuffer(gl.ARRAY_BUFFER, buffer);
    gl.bufferData(gl.ARRAY_BUFFER, 1024, gl.STATIC_DRAW);

### Getting buffer information

To check the current buffer usage and buffer size, use the [`WebGLRenderingContext.getBufferParameter()`](getbufferparameter) method.

    gl.getBufferParameter(gl.ARRAY_BUFFER, gl.BUFFER_SIZE);
    gl.getBufferParameter(gl.ARRAY_BUFFER, gl.BUFFER_USAGE);

### Getting size of a typed array

To calculate size parameter for a typed array.

    var dataArray = new Float32Array([1, 2, 3, 4]);
    var sizeInBytes = dataArray.length * dataArray.BYTES_PER_ELEMENT;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.5">WebGL 1.0<br />
<span class="small">The definition of 'bufferData' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glBufferData.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glBufferData' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glBufferData.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glBufferData' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3 API.<br />
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

`bufferData`

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
-   [`WebGLRenderingContext.bufferSubData()`](buffersubdata)
-   Other buffers: [`WebGLFramebuffer`](../webglframebuffer), [`WebGLRenderbuffer`](../webglrenderbuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/bufferData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/bufferData</a>
