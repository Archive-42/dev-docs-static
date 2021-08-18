WebGL2RenderingContext.getBufferSubData()
=========================================

The `WebGL2RenderingContext.getBufferSubData()` method of the [WebGL 2 API](../webgl_api) reads data from a buffer binding point and writes them to an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) or [`SharedArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer).

Syntax
------

    void gl.getBufferSubData(target, srcByteOffset, ArrayBufferView dstData, optional dstOffset, optional length);

### Parameters

`target`  
A [`GLenum`](../webgl_api/types) specifying the binding point (target). Possible values:

-   `gl.ARRAY_BUFFER`: Buffer containing vertex attributes, such as vertex coordinates, texture coordinate data, or vertex color data.
-   `gl.ELEMENT_ARRAY_BUFFER`: Buffer used for element indices.
-   `gl.COPY_READ_BUFFER`: Buffer for copying from one buffer object to another.
-   `gl.COPY_WRITE_BUFFER`: Buffer for copying from one buffer object to another.
-   `gl.TRANSFORM_FEEDBACK_BUFFER`: Buffer for transform feedback operations.
-   `gl.UNIFORM_BUFFER`: Buffer used for storing uniform blocks.
-   `gl.PIXEL_PACK_BUFFER`: Buffer used for pixel transfer operations.
-   `gl.PIXEL_UNPACK_BUFFER`: Buffer used for pixel transfer operations.

`srcByteOffset`  
A [`GLintptr`](../webgl_api/types) specifying the byte offset from which to start reading from the buffer.

`dstData`  
An [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) or [`SharedArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer) to which to write the buffer data.

srcOffset <span class="badge inline optional">Optional</span>   
A [`GLuint`](../webgl_api/types) specifying the element index offset where to start reading the buffer.

 `length` <span class="badge inline optional">Optional</span>   
A [`GLuint`](../webgl_api/types) defaulting to 0.

### Return value

None.

### Exceptions

An `INVALID_VALUE` error is generated if:

-   `offset` + `returnedData.byteLength `would extend beyond the end of the buffer
-   `returnedData` is [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null)
-   `offset` is less than zero.

An `INVALID_OPERATION` error is generated if:

-   zero is bound to `target`
-   `target` is `TRANSFORM_FEEDBACK_BUFFER`, and any transform feedback object is currently active.

Examples
--------

    var buffer = gl.createBuffer();
    gl.bindBuffer(gl.ARRAY_BUFFER, buffer);
    gl.bufferData(gl.ARRAY_BUFFER, new Float32Array(vertices), gl.STATIC_DRAW);

    var arrBuffer = new ArrayBuffer(vertices.length * Float32Array.BYTES_PER_ELEMENT);
    gl.getBufferSubData(gl.ARRAY_BUFFER, 0, arrBuffer);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.3">WebGL 2.0<br />
<span class="small">The definition of 'getBufferSubData' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getBufferSubData`

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

`SharedArrayBuffer_as_param`

60

79

79

No

47

No

60

60

?

44

No

8.0

See also
--------

-   [`WebGLRenderingContext.bufferData()`](../webglrenderingcontext/bufferdata)
-   [`WebGLRenderingContext.bufferSubData()`](../webglrenderingcontext/buffersubdata)
-   [`WebGLRenderingContext.getBufferParameter()`](../webglrenderingcontext/getbufferparameter)
-   [`WebGL2RenderingContext.copyBufferSubData()`](copybuffersubdata)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getBufferSubData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getBufferSubData</a>
