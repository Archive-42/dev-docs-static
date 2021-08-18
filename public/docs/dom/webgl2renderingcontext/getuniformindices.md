WebGL2RenderingContext.getUniformIndices()
==========================================

The `WebGL2RenderingContext.getUniformIndices()` method of the [WebGL 2 API](../webgl_api) retrieves the indices of a number of uniforms within a [`WebGLProgram`](../webglprogram).

Syntax
------

    sequence<GLuint> gl.getUniformIndices(program, uniformNames);

### Parameters

`program`  
A [`WebGLProgram`](../webglprogram) containing uniforms whose indices to query.

`uniformNames`  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`DOMString`](../domstring) specifying the names of the uniforms to query.

### Return value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLuint`](../webgl_api/types) containing the uniform indices.

Examples
--------

    var uniformIndices = gl.getUniformIndices(program, ['UBORed', 'UBOGreen', 'UBOBlue']);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.16">WebGL 2.0<br />
<span class="small">The definition of 'getUniformIndices' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetUniformIndices.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetUniformIndices' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`getUniformIndices`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getUniformIndices" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getUniformIndices</a>
