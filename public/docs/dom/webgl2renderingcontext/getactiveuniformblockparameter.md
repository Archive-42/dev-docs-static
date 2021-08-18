WebGL2RenderingContext.getActiveUniformBlockParameter()
=======================================================

The `WebGL2RenderingContext.getActiveUniformBlockParameter()` method of the [WebGL 2 API](../webgl_api) retrieves information about an active uniform block within a [`WebGLProgram`](../webglprogram).

Syntax
------

    any gl.getActiveUniformBlockParameter(program, uniformBlockIndex, pname);

### Parameters

`program`  
A [`WebGLProgram`](../webglprogram) containing the active uniform block.

`uniformBlockIndex`  
A [`GLuint`](../webgl_api/types) specifying the index of the active uniform block within the program.

`pname`  
A [`GLenum`](../webgl_api/types) specifying which information to query. Possible values:

-   `gl.UNIFORM_BLOCK_BINDING`: Returns a [`GLuint`](../webgl_api/types) indicating the uniform buffer binding point.
-   `gl.UNIFORM_BLOCK_DATA_SIZE`: Returns a [`GLuint`](../webgl_api/types) indicating the minimum total buffer object size.
-   `gl.UNIFORM_BLOCK_ACTIVE_UNIFORMS`: Returns a [`GLuint`](../webgl_api/types) indicating the number of active uniforms in the uniform block.
-   `gl.UNIFORM_BLOCK_ACTIVE_UNIFORM_INDICES`: Returns a [`Uint32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint32Array) indicating the list of active uniforms in the uniform block.
-   `gl.UNIFORM_BLOCK_REFERENCED_BY_VERTEX_SHADER`: Returns a [`GLboolean`](../webgl_api/types) indicating whether the uniform block is referenced by the vertex shader.
-   `gl.UNIFORM_BLOCK_REFERENCED_BY_FRAGMENT_SHADER`: Returns a [`GLboolean`](../webgl_api/types) indicating whether the uniform block is referenced by the fragment shader.

### Return value

Depends on which information is requested using the `pname` parameter. If an error occurs, [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) is returned.

Examples
--------

    var blockSize = gl.getActiveUniformBlockParameter(program,
                          blockIndex, gl.UNIFORM_BLOCK_DATA_SIZE);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.16">WebGL 2.0<br />
<span class="small">The definition of 'getActiveUniformBlockParameter' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetActiveUniformBlockiv.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetActiveUniformBlockiv' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`getActiveUniformBlockParameter`

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

-   [`WebGL2RenderingContext.getActiveUniforms()`](getactiveuniforms)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getActiveUniformBlockParameter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getActiveUniformBlockParameter</a>
