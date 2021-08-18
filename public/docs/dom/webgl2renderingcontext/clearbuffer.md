WebGL2RenderingContext.clearBuffer\[fiuv\]()
============================================

The `WebGL2RenderingContext.clearBuffer[fiuv]()` methods of the [WebGL 2 API](../webgl_api) clear buffers from the currently bound framebuffer.

Syntax
------

    void gl.clearBufferfv(buffer, drawbuffer, values, optional srcOffset);
    void gl.clearBufferiv(buffer, drawbuffer, values, optional srcOffset);
    void gl.clearBufferuiv(buffer, drawbuffer, values, optional srcOffset);
    void gl.clearBufferfi(buffer, drawbuffer, depth, stencil);

### Parameters

`buffer`  
A [`GLenum`](../webgl_api/types) specifying the buffer to clear. Possible values are:

-   `gl.COLOR`: Color buffer.
-   `gl.DEPTH`: Depth buffer.
-   `gl.STENCIL`: Stencil buffer.
-   `gl.DEPTH_STENCIL`: clears depth and stencil buffers (used with `clearBufferfi`).

`drawBuffer`  
A [`GLint`](../webgl_api/types) specifying the draw buffer to clear.

`values`  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLint`](../webgl_api/types), [`GLuint`](../webgl_api/types) or [`GLfloat`](../webgl_api/types) values or  
an [`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array), [`Uint32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint32Array) or [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) specifying the values to clear to.

`depth`  
A [`GLfloat`](../webgl_api/types) specifying the value to clear a depth render buffer to.

`stencil`  
A [`GLint`](../webgl_api/types) specifying the value to clear the stencil render buffer to.

### Return value

None.

Examples
--------

    gl.clearBufferiv(gl.COLOR, 0, new Int32Array([r, g, b, a]));
    gl.clearBufferuiv(gl.COLOR, 0, new Uint32Array([r, g, b, a]));
    gl.clearBufferfv(gl.COLOR, 0, new Float32Array([r, g, b, a]));
    gl.clearBufferfv(gl.COLOR, 0, [0.0, 0.0, 0.0, 0.0]);
    gl.clearBufferfi(gl.DEPTH_STENCIL, 0, 1.0, 0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.11">WebGL 2.0<br />
<span class="small">The definition of 'clearBuffer[fiuv]()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glClearBuffer.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glClearBuffer' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`clearBuffer`

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

-   [`WebGL2RenderingContext.drawBuffers()`](drawbuffers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/clearBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/clearBuffer</a>
