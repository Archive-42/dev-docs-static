WebGL2RenderingContext.getActiveUniformBlockName()
==================================================

The `WebGL2RenderingContext.getActiveUniformBlockName()` method of the [WebGL 2 API](../webgl_api) retrieves the name of the active uniform block at a given index within a [`WebGLProgram`](../webglprogram).

Syntax
------

    DOMString gl.getActiveUniformBlockName(program, uniformBlockIndex);

### Parameters

`program`  
A [`WebGLProgram`](../webglprogram) containing the uniform block.

`uniformBlockIndex`  
A [`GLuint`](../webgl_api/types) specifying the index of the uniform block to whose name to retrieve.

### Return value

A [`DOMString`](../domstring) indicating the active uniform block name.

Examples
--------

    var blockName = gl.getActiveUniformBlockName(program, 0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.16">WebGL 2.0<br />
<span class="small">The definition of 'getActiveUniformBlockName' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetActiveUniformBlockName.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetActiveUniformBlockName' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`getActiveUniformBlockName`

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

-   [`WebGL2RenderingContext.getUniformBlockIndex()`](getuniformblockindex)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getActiveUniformBlockName" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getActiveUniformBlockName</a>
