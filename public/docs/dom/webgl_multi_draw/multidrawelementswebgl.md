WEBGL\_multi\_draw.multiDrawElementsWEBGL()
===========================================

The `WEBGL_multi_draw.multiDrawElementsWEBGL()` method of the [WebGL API](../webgl_api) renders multiple primitives from array data. It is identical to multiple calls to the [`gl.drawElements()`](../webglrenderingcontext/drawelements) method.

Syntax
------

    void ext.multiDrawElementsWEBGL(mode,
        countsList, countsOffset,
        type,
        firstsList, firstsOffset,
        drawCount);

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

`countsList`  
An [`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array) or [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) (of [`GLint`](../webgl_api/types)) specifying a list of numbers of indices to be rendered.

`countsOffset`  
A [`GLUint`](../webgl_api/types) defining the starting point into the `countsList` array.

type  
A [`GLenum`](../webgl_api/types) specifying the type of the values in the element array buffer. Possible values are:

-   `gl.UNSIGNED_BYTE`
-   `gl.UNSIGNED_SHORT`
-   When using the [`OES_element_index_uint`](../oes_element_index_uint) extension:
    -   `gl.UNSIGNED_INT`

`offsetsList`  
An [`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array) or [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) (of [`GLsizei`](../webgl_api/types)) specifying a list of starting indices for the arrays of vector points.

`offsetsOffset`  
A [`GLuint`](../webgl_api/types) defining the starting point into the `offsetsList` array.

`drawCount`  
A [`GLsizei`](../webgl_api/types) specifying the number of instances of the range of elements to execute.

### Return value

None.

### Exceptions

-   If `mode` is not one of the accepted values, a `gl.INVALID_ENUM` error is thrown.
-   If `drawCount` or items in `countsList` or `offsetsList` are negative, a `gl.INVALID_VALUE` error is thrown.

Examples
--------

    // let counts = new Int32Array(...);
    // let offsets = new Int32Array(...);
    ext.multiDrawElementsWEBGL(
        gl.TRIANGLES, counts, 0, gl.UNSIGNED_SHORT, offsets, 0, counts.length);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_multi_draw/">WEBGL_multi_draw<br />
<span class="small">The definition of 'WEBGL_multi_draw' in that specification.</span></a></td></tr></tbody></table>

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

`multiDrawElementsWEBGL`

86

86

No

No

72

No

86

86

No

No

No

14.0

See also
--------

-   [`WebGLRenderingContext.drawElements()`](../webglrenderingcontext/drawelements)
-   [`WebGL2RenderingContext.drawElementsInstanced()`](../webgl2renderingcontext/drawelementsinstanced)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_multi_draw/multiDrawElementsWEBGL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_multi_draw/multiDrawElementsWEBGL</a>
