WebGL2RenderingContext.uniformBlockBinding()
============================================

The `WebGL2RenderingContext.uniformBlockBinding()` method of the [WebGL 2 API](../webgl_api) assigns binding points for active uniform blocks.

Syntax
------

    void gl.uniformBlockBinding(program, uniformBlockIndex, uniformBlockBinding);

### Parameters

`program`  
A [`WebGLProgram`](../webglprogram) containing the active uniform block whose binding to assign.

`uniformBlockIndex`  
A [`GLuint`](../webgl_api/types) specifying the index of the active uniform block within the program.

uniformBlockBinding  
A [`GLuint`](../webgl_api/types) specifying the binding point to which to bind the uniform block.

### Return value

None.

Examples
--------

    gl.uniformBlockBinding(program, 0, 1);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.16">WebGL 2.0<br />
<span class="small">The definition of 'uniformBlockBinding' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glUniformBlockBinding.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glUniformBlockBinding' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`uniformBlockBinding`

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

-   [`WebGL2RenderingContext.getUniformIndices()`](getuniformindices)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/uniformBlockBinding" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/uniformBlockBinding</a>
