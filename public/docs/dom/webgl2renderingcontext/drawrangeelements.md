WebGL2RenderingContext.drawRangeElements()
==========================================

The `WebGL2RenderingContext.drawRangeElements()` method of the [WebGL API](../webgl_api) renders primitives from array data in a given range.

Syntax
------

    void gl.drawRangeElements(mode, start, end, count, type, offset);

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

`start`  
A [`GLuint`](../webgl_api/types) specifying the minimum array index contained in `offset`.

`end`  
A [`GLuint`](../webgl_api/types) specifying the maximum array index contained in `offset`.

count  
A [`GLsizei`](../webgl_api/types) specifying the number of elements to be rendered.

type  
A [`GLenum`](../webgl_api/types) specifying the type of the values in the element array buffer. Possible values are:

-   `gl.UNSIGNED_BYTE`
-   `gl.UNSIGNED_SHORT`
-   `gl.UNSIGNED_INT`

offset  
A [`GLintptr`](../webgl_api/types) specifying an offset in the element array buffer. Must be a valid multiple of the size of the given `type`.

### Return value

None.

### Exceptions

-   If `mode` is not one of the accepted values, a `gl.INVALID_ENUM` error is thrown.
-   If `offset` is a valid multiple of the size of the given type, a `gl.INVALID_OPERATION` error is thrown.
-   If `count` is negative, a `gl.INVALID_VALUE` error is thrown.

Examples
--------

    gl.drawRangeElements(gl.POINTS, 0, 7, 8, gl.UNSIGNED_BYTE, 0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.9">WebGL 2.0<br />
<span class="small">The definition of 'drawRangeElements' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glDrawRangeElements.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glDrawRangeElements' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`drawRangeElements`

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

-   [`WebGLRenderingContext.drawElements()`](../webglrenderingcontext/drawelements)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/drawRangeElements" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/drawRangeElements</a>
