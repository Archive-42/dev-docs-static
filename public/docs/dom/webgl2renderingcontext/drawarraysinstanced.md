WebGL2RenderingContext.drawArraysInstanced()
============================================

The `WebGL2RenderingContext.drawArraysInstanced()` method of the [WebGL 2 API](../webgl_api) renders primitives from array data like the [`gl.drawArrays()`](../webglrenderingcontext/drawarrays) method. In addition, it can execute multiple instances of the range of elements.

**Note:** When using [WebGL 1](../webglrenderingcontext), the [`ANGLE_instanced_arrays`](../angle_instanced_arrays) extension can provide this method, too.

Syntax
------

    void gl.drawArraysInstanced(mode, first, count, instanceCount);

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

instanceCount  
A [`GLsizei`](../webgl_api/types) specifying the number of instances of the range of elements to execute.

### Return value

None.

Examples
--------

    gl.drawArraysInstanced(gl.POINTS, 0, 8, 4);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.9">WebGL 2.0<br />
<span class="small">The definition of 'drawArraysInstanced' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glDrawArraysInstanced.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glDrawArraysInstanced' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`drawArraysInstanced`

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

-   [`ANGLE_instanced_arrays.drawArraysInstancedANGLE()`](../angle_instanced_arrays/drawarraysinstancedangle)
-   [`WEBGL_multi_draw.multiDrawArraysInstancedWEBGL()`](../webgl_multi_draw/multidrawarraysinstancedwebgl)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/drawArraysInstanced" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/drawArraysInstanced</a>
