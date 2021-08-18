WebGL2RenderingContext.getUniformBlockIndex()
=============================================

The `WebGL2RenderingContext.getUniformBlockIndex()` method of the [WebGL 2 API](../webgl_api) retrieves the index of a uniform block within a [`WebGLProgram`](../webglprogram).

Syntax
------

    GLuint gl.getUniformBlockIndex(program, uniformBlockName);

### Parameters

`program`  
A [`WebGLProgram`](../webglprogram) containing the uniform block.

`uniformName`  
A [`DOMString`](../domstring) specifying the name of the uniform block to whose index to retrieve.

### Return value

A [`GLuint`](../webgl_api/types) indicating the uniform block index.

Examples
--------

    // Assuming a shader with the following declaration:
    // uniform UBOData {
    //   mat4 foo;
    // } instanceName;

    // use the block name, not the instance name:
    var blockIndex = gl.getUniformBlockIndex(program, 'UBOData');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.16">WebGL 2.0<br />
<span class="small">The definition of 'getUniformBlockIndex' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetUniformBlockIndex.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetUniformBlockIndex' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`getUniformBlockIndex`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getUniformBlockIndex" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getUniformBlockIndex</a>
