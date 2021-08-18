WebGL2RenderingContext.getActiveUniforms()
==========================================

The `WebGL2RenderingContext.getActiveUniforms()` method of the [WebGL 2 API](../webgl_api) retrieves information about active uniforms within a [`WebGLProgram`](../webglprogram).

Syntax
------

    any gl.getActiveUniforms(program, uniformIndices, pname);

### Parameters

`program`  
A [`WebGLProgram`](../webglprogram) containing the active uniforms.

`uniformIndices`  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLuint`](../webgl_api/types) specifying the indices of the active uniforms to query.

`pname`  
A [`GLenum`](../webgl_api/types) specifying which information to query. Possible values:

-   `gl.UNIFORM_TYPE`: Returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLenum`](../webgl_api/types) indicating the [types of the uniforms](../webglrenderingcontext/getuniform#return_value).
-   `gl.UNIFORM_SIZE`: Returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLuint`](../webgl_api/types) indicating the sizes of the uniforms.
-   `gl.UNIFORM_BLOCK_INDEX`: Returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLint`](../webgl_api/types) indicating the block indices of the uniforms.
-   `gl.UNIFORM_OFFSET`: Returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLint`](../webgl_api/types) indicating the uniform buffer offsets.
-   `gl.UNIFORM_ARRAY_STRIDE`: Returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLint`](../webgl_api/types) indicating the strides between the elements.
-   `gl.UNIFORM_MATRIX_STRIDE`: Returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLint`](../webgl_api/types) indicating the strides between columns of a column-major matrix or a row-major matrix.
-   `gl.UNIFORM_IS_ROW_MAJOR`: Returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLboolean`](../webgl_api/types) indicating whether each of the uniforms is a row-major matrix or not.

### Return value

Depends on which information is requested using the `pname` parameter.

Examples
--------

    var uniformIndices = gl.getUniformIndices(program, ['UBORed', 'UBOGreen', 'UBOBlue']);
    var uniformOffsets = gl.getActiveUniforms(program, uniformIndices, gl.UNIFORM_OFFSET);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.16">WebGL 2.0<br />
<span class="small">The definition of 'getActiveUniforms' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetActiveUniformsiv.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetActiveUniformsiv' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`getActiveUniforms`

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

-   [`WebGL2RenderingContext.getActiveUniformBlockParameter()`](getactiveuniformblockparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getActiveUniforms" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getActiveUniforms</a>
