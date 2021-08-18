WebGLRenderingContext.bufferSubData()
=====================================

The `WebGLRenderingContext.bufferSubData()` method of the [WebGL API](../webgl_api) updates a subset of a buffer object's data store.

Syntax
------

    // WebGL1:
    void gl.bufferSubData(target, offset, ArrayBuffer srcData);
    void gl.bufferSubData(target, offset, ArrayBufferView srcData);

    // WebGL2:
    void gl.bufferSubData(target, dstByteOffset, ArrayBufferView srcData, srcOffset, length);

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

dstByteOffset  
A [`GLintptr`](../webgl_api/types) specifying an offset in bytes where the data replacement will start.

srcData <span class="badge inline optional">Optional</span>   
An [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), [`SharedArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer) or one of the [`ArrayBufferView`](../arraybufferview) typed array types that will be copied into the data store.

srcOffset  
A [`GLuint`](../webgl_api/types) specifying the element index offset where to start reading the buffer.

 `length` <span class="badge inline optional">Optional</span>   
A [`GLuint`](../webgl_api/types) defaulting to 0.

### Return value

None.

### Exceptions

-   A `gl.INVALID_VALUE` error is thrown if the data would be written past the end of the buffer or if `data` is `null`.
-   A `gl.INVALID_ENUM` error is thrown if `target` is not one of the allowed enums.

Examples
--------

### Using `bufferSubData`

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    var buffer = gl.createBuffer();
    gl.bindBuffer(gl.ARRAY_BUFFER, buffer);
    gl.bufferData(gl.ARRAY_BUFFER, 1024, gl.STATIC_DRAW);
    gl.bufferSubData(gl.ARRAY_BUFFER, 512, data);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.5">WebGL 1.0<br />
<span class="small">The definition of 'bufferSubData' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glBufferSubData.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glBufferSubData' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL ES 2 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glBufferSubData.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glBufferSubData' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3 API.<br />
<br />
Adds new <code>target</code> buffers:<br />
<code>gl.COPY_READ_BUFFER</code>,<br />
<code>gl.COPY_WRITE_BUFFER</code>,<br />
<code>gl.TRANSFORM_FEEDBACK_BUFFER</code>,<br />
<code>gl.UNIFORM_BUFFER</code>,<br />
<code>gl.PIXEL_PACK_BUFFER</code>,<br />
<code>gl.PIXEL_UNPACK_BUFFER</code>.</td></tr></tbody></table>

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

`bufferSubData`

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
-   [`WebGLRenderingContext.bufferData()`](bufferdata)
-   Other buffers: [`WebGLFramebuffer`](../webglframebuffer), [`WebGLRenderbuffer`](../webglrenderbuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/bufferSubData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/bufferSubData</a>
