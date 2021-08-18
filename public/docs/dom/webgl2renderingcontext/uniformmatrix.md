WebGL2RenderingContext.uniformMatrix\[234\]x\[234\]fv()
=======================================================

The `WebGL2RenderingContext.uniformMatrix[234]x[234]fv()` methods of the [WebGL 2 API](../webgl_api) specify matrix values for uniform variables.

There are no `2x2`, `3x3`, and `4x4` versions of this method. They are abbreviated in `2`, `3`, and `4`, respectively. See the syntax below.

Syntax
------

    void gl.uniformMatrix2fv(location, transpose, data, optional srcOffset, optional srcLength);
    void gl.uniformMatrix3x2fv(location, transpose, data, optional srcOffset, optional srcLength);
    void gl.uniformMatrix4x2fv(location, transpose, data, optional srcOffset, optional srcLength);
    void gl.uniformMatrix2x3fv(location, transpose, data, optional srcOffset, optional srcLength);
    void gl.uniformMatrix3fv(location, transpose, data, optional srcOffset, optional srcLength);
    void gl.uniformMatrix4x3fv(location, transpose, data, optional srcOffset, optional srcLength);
    void gl.uniformMatrix2x4fv(location, transpose, data, optional srcOffset, optional srcLength);
    void gl.uniformMatrix3x4fv(location, transpose, data, optional srcOffset, optional srcLength);
    void gl.uniformMatrix4fv(location, transpose, data, optional srcOffset, optional srcLength);

### Parameters

location  
A [`WebGLUniformLocation`](../webgluniformlocation) object containing the location of the uniform attribute to modify.

transpose  
A [`GLboolean`](../webgl_api/types) specifying whether to transpose the matrix. Must be `false`.

data  
A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) of float values.

### Return value

None.

Examples
--------

    gl.uniformMatrix2x3fv(loc, false, [1, 2, 3, 4, 5, 6]);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.8">WebGL 2.0<br />
<span class="small">The definition of 'uniformMatrix' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glUniform.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glUniformMatrix' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`uniformMatrix`

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

-   [`WebGLRenderingContext.uniformMatrix()`](../webglrenderingcontext/uniformmatrix)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/uniformMatrix" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/uniformMatrix</a>
