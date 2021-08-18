WebGLRenderingContext.drawElements()
====================================

The `WebGLRenderingContext.drawElements()` method of the [WebGL API](../webgl_api) renders primitives from array data.

Syntax
------

    void gl.drawElements(mode, count, type, offset);

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
A [`GLintptr`](../webgl_api/types) specifying a byte offset in the element array buffer. Must be a valid multiple of the size of the given `type`.

### Return value

None.

### Exceptions

-   If `mode` is not one of the accepted values, a `gl.INVALID_ENUM` error is thrown.
-   If `offset` is not a valid multiple of the size of the given type, a `gl.INVALID_OPERATION` error is thrown.
-   If `count` is negative, a `gl.INVALID_VALUE` error is thrown.

Examples
--------

    gl.drawElements(gl.POINTS, 8, gl.UNSIGNED_BYTE, 0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.11">WebGL 1.0<br />
<span class="small">The definition of 'drawElements' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glDrawElements.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glDrawElements' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`drawElements`

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

-   [`WebGLRenderingContext.drawArrays()`](drawarrays)
-   [`OES_element_index_uint`](../oes_element_index_uint)
-   [`WEBGL_multi_draw.multiDrawElementsWEBGL()`](../webgl_multi_draw/multidrawelementswebgl)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/drawElements" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/drawElements</a>
