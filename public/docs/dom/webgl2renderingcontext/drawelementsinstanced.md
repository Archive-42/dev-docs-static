WebGL2RenderingContext.drawElementsInstanced()
==============================================

The `WebGL2RenderingContext.drawElementsInstanced()` method of the [WebGL 2 API](../webgl_api) renders primitives from array data like the [`gl.drawElements()`](../webglrenderingcontext/drawelements) method. In addition, it can execute multiple instances of a set of elements.

**Note:** When using [WebGL 1](../webglrenderingcontext), the [`ANGLE_instanced_arrays`](../angle_instanced_arrays) extension can provide this method, too.

Syntax
------

    void gl.drawElementsInstanced(mode, count, type, offset, instanceCount);

### Parameters

`mode`  
A [`GLenum`](../webgl_api/types) specifying the type primitive to render. Possible values are:

-   `gl.POINTS`: Draws a single dot.
-   `gl.LINE_STRIP`: Draws a straight line to the next vertex.
-   `gl.LINE_LOOP`: Draws a straight line to the next vertex, and connects the last vertex back to the first.
-   `gl.LINES`: Draws a line between a pair of vertices.
-   `gl.TRIANGLE_STRIP`
-   `gl.TRIANGLE_FAN`
-   `gl.TRIANGLES`: Draws a triangle for a group of three vertices.

count  
A [`GLsizei`](../webgl_api/types) specifying the number of elements to be rendered.

type  
A [`GLenum`](../webgl_api/types) specifying the type of the values in the element array buffer. Possible values are:

-   `gl.UNSIGNED_BYTE`
-   `gl.UNSIGNED_SHORT`
-   When using the [`OES_element_index_uint`](../oes_element_index_uint) extension:
    -   `gl.UNSIGNED_INT`

offset  
A [`GLintptr`](../webgl_api/types) specifying an offset in the element array buffer. Must be a valid multiple of the size of the given `type`.

instanceCount  
A [`GLsizei`](../webgl_api/types) specifying the number of instances of the set of elements to execute.

### Return value

None.

### Exceptions

-   If `mode` is not one of the accepted values, a `gl.INVALID_ENUM` error is thrown.
-   If `offset` is a valid multiple of the size of the given type, a `gl.INVALID_OPERATION` error is thrown.
-   If `count` or `instanceCount` are negative, a `gl.INVALID_VALUE` error is thrown.

Examples
--------

    gl.drawElementsInstanced(gl.POINTS, 2, gl.UNSIGNED_SHORT, 0, 4);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.9">WebGL 2.0<br />
<span class="small">The definition of 'drawElementsInstanced' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glDrawElementsInstanced.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glDrawElementsInstanced' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`drawElementsInstanced`

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

-   [`ext.drawArraysInstancedANGLE()`](../angle_instanced_arrays/drawarraysinstancedangle)
-   [`ext.vertexAttribDivisorANGLE()`](../angle_instanced_arrays/vertexattribdivisorangle)
-   [`WebGLRenderingContext.drawArrays()`](../webglrenderingcontext/drawarrays)
-   [`WebGLRenderingContext.drawElements()`](../webglrenderingcontext/drawelements)
-   [`WebGL2RenderingContext.drawArraysInstanced()`](drawarraysinstanced)
-   [`WebGL2RenderingContext.vertexAttribDivisor()`](vertexattribdivisor)
-   [`WEBGL_multi_draw.multiDrawElementsInstancedWEBGL()`](../webgl_multi_draw/multidrawelementsinstancedwebgl)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/drawElementsInstanced" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/drawElementsInstanced</a>
