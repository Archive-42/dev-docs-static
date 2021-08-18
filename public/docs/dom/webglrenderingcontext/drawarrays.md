WebGLRenderingContext.drawArrays()
==================================

The `WebGLRenderingContext.drawArrays()` method of the [WebGL API](../webgl_api) renders primitives from array data.

Syntax
------

    void gl.drawArrays(mode, first, count);

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

first  
A [`GLint`](../webgl_api/types) specifying the starting index in the array of vector points.

count  
A [`GLsizei`](../webgl_api/types) specifying the number of indices to be rendered.

### Return value

None.

### Exceptions

-   If `mode` is not one of the accepted values, a `gl.INVALID_ENUM` error is thrown.
-   If `first` or `count` are negative, a `gl.INVALID_VALUE` error is thrown.
-   if `gl.CURRENT_PROGRAM` is [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null), a `gl.INVALID_OPERATION` error is thrown.

Examples
--------

    gl.drawArrays(gl.POINTS, 0, 8);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.11">WebGL 1.0<br />
<span class="small">The definition of 'drawArrays' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glDrawArrays.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glDrawArrays' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`drawArrays`

9

12

4

11

12

5.1

≤37

25

Yes

12

8

1.5

See also
--------

-   [`WebGLRenderingContext.drawElements()`](drawelements)
-   [`ext.drawArraysInstancedANGLE()`](../angle_instanced_arrays/drawarraysinstancedangle)
-   [`ext.drawElementsInstancedANGLE()`](../angle_instanced_arrays/drawelementsinstancedangle)
-   [`ext.vertexAttribDivisorANGLE()`](../angle_instanced_arrays/vertexattribdivisorangle)
-   [`WebGL2RenderingContext.drawArraysInstanced()`](../webgl2renderingcontext/drawarraysinstanced)
-   [`WebGL2RenderingContext.drawElementsInstanced()`](../webgl2renderingcontext/drawelementsinstanced)
-   [`WebGL2RenderingContext.vertexAttribDivisor()`](../webgl2renderingcontext/vertexattribdivisor)
-   [`WEBGL_multi_draw.multiDrawArraysWEBGL()`](../webgl_multi_draw/multidrawarrayswebgl)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/drawArrays" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/drawArrays</a>
