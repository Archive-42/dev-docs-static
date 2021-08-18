WebGL2RenderingContext.copyBufferSubData()
==========================================

The `WebGL2RenderingContext.copyBufferSubData()` method of the [WebGL 2 API](../webgl_api) copies part of the data of a buffer to another buffer.

Syntax
------

    void gl.copyBufferSubData(readTarget, writeTarget, readOffset, writeOffset, size);

### Parameters

`readTarget  writeTarget`  
A [`GLenum`](../webgl_api/types) specifying the binding point (target) from whose data store should be read or written. Possible values:

-   `gl.ARRAY_BUFFER`: Buffer containing vertex attributes, such as vertex coordinates, texture coordinate data, or vertex color data.
-   `gl.ELEMENT_ARRAY_BUFFER`: Buffer used for element indices.
-   `gl.COPY_READ_BUFFER`: Buffer for copying from one buffer object to another (provided specifically for copy operations).
-   `gl.COPY_WRITE_BUFFER`: Buffer for copying from one buffer object to another (provided specifically for copy operations).
-   `gl.TRANSFORM_FEEDBACK_BUFFER`: Buffer for transform feedback operations.
-   `gl.UNIFORM_BUFFER`: Buffer used for storing uniform blocks.
-   `gl.PIXEL_PACK_BUFFER`: Buffer used for pixel transfer operations.
-   `gl.PIXEL_UNPACK_BUFFER`: Buffer used for pixel transfer operations.

`readOffset  writeOffset`  
A [`GLintptr`](../webgl_api/types) specifying the byte offset from which to start reading from or writing to the buffer.

`size`  
A [`GLsizei`](../webgl_api/types) in bytes specifying the size of the data to be copied from `readTarget` to `writeTarget`.

### Return value

None.

Examples
--------

    var srcBuffer = gl.createBuffer();
    var dstBuffer = gl.createBuffer();

    var data = new Float32Array(vertices);
    var length = vertices.length * 4;

    gl.bindBuffer(gl.ARRAY_BUFFER, srcBuffer);
    gl.bufferData(gl.ARRAY_BUFFER, data, gl.STATIC_DRAW);
    gl.bindBuffer(gl.COPY_READ_BUFFER, srcBuffer);

    gl.bindBuffer(gl.ARRAY_BUFFER, dstBuffer);
    gl.bufferData(gl.ARRAY_BUFFER, new Float32Array(length), gl.STATIC_DRAW);

    gl.copyBufferSubData(gl.COPY_READ_BUFFER, gl.ARRAY_BUFFER, 0, 0, length);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.3">WebGL 2.0<br />
<span class="small">The definition of 'copyBufferSubData' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glCopyBufferSubData.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glCopyBufferSubData' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`copyBufferSubData`

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

-   [`WebGLRenderingContext.bufferData()`](../webglrenderingcontext/bufferdata)
-   [`WebGLRenderingContext.bufferSubData()`](../webglrenderingcontext/buffersubdata)
-   [`WebGLRenderingContext.getBufferParameter()`](../webglrenderingcontext/getbufferparameter)
-   [`WebGL2RenderingContext.getBufferSubData()`](getbuffersubdata)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/copyBufferSubData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/copyBufferSubData</a>
