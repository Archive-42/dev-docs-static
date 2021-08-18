WebGLRenderingContext.getVertexAttrib()
=======================================

The `WebGLRenderingContext.getVertexAttrib()` method of the [WebGL API](../webgl_api) returns information about a vertex attribute at a given position.

Syntax
------

    any gl.getVertexAttrib(index, pname);

### Parameters

`index`  
A [`GLuint`](../webgl_api/types) specifying the index of the vertex attribute.

`pname`  
A [`GLenum`](../webgl_api/types) specifying the information to query. Possible values:

-   `gl.VERTEX_ATTRIB_ARRAY_BUFFER_BINDING`: Returns the currently bound [`WebGLBuffer`](../webglbuffer).
-   `gl.VERTEX_ATTRIB_ARRAY_ENABLED`: Returns a [`GLboolean`](../webgl_api/types) that is `true` if the vertex attribute is enabled at this `index`. Otherwise `false`.
-   `gl.VERTEX_ATTRIB_ARRAY_SIZE`: Returns a [`GLint`](../webgl_api/types) indicating the size of an element of the vertex array.
-   `gl.VERTEX_ATTRIB_ARRAY_STRIDE`: Returns a [`GLint`](../webgl_api/types) indicating the number of bytes between successive elements in the array. 0 means that the elements are sequential.
-   `gl.VERTEX_ATTRIB_ARRAY_TYPE`: Returns a [`GLenum`](../webgl_api/types) representing the array type. One of
    -   `gl.BYTE`,
    -   `gl.UNSIGNED_BYTE`,
    -   `gl.SHORT`,
    -   `gl.UNSIGNED_SHORT`,
    -   `gl.FLOAT`.
-   `gl.VERTEX_ATTRIB_ARRAY_NORMALIZED`: Returns a [`GLboolean`](../webgl_api/types) that is true if fixed-point data types are normalized for the vertex attribute array at the given `index`.
-   `gl.CURRENT_VERTEX_ATTRIB`: Returns a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) (with 4 elements) representing the current value of the vertex attribute at the given `index`.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.VERTEX_ATTRIB_ARRAY_INTEGER`: Returns a [`GLboolean`](../webgl_api/types) indicating whether or not an integer data type is in the vertex attribute array at the given `index`.
    -   `gl.VERTEX_ATTRIB_ARRAY_DIVISOR`: Returns a [`GLint`](../webgl_api/types) describing the frequency divisor used for instanced rendering.
-   When using the [`ANGLE_instanced_arrays`](../angle_instanced_arrays) extension:
    -   `ext.VERTEX_ATTRIB_ARRAY_DIVISOR_ANGLE`: Returns a [`GLint`](../webgl_api/types) describing the frequency divisor used for instanced rendering.

### Return value

Returns the requested vertex attribute information (as specified with `pname`).

Examples
--------

    gl.getVertexAttrib(0, gl.VERTEX_ATTRIB_ARRAY_BUFFER_BINDING);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.10">WebGL 1.0<br />
<span class="small">The definition of 'getVertexAttrib' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetVertexAttrib.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetVertexAttrib' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL ES 2 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.8">WebGL 2.0<br />
<span class="small">The definition of 'getVertexAttrib' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Updated definition for WebGL 2.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetVertexAttrib.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetVertexAttrib' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL ES 3 API.</td></tr></tbody></table>

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

`getVertexAttrib`

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

`WebGL2`

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

-   [`WebGLRenderingContext.getVertexAttribOffset()`](getvertexattriboffset)
-   [`ANGLE_instanced_arrays`](../angle_instanced_arrays)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getVertexAttrib" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getVertexAttrib</a>
