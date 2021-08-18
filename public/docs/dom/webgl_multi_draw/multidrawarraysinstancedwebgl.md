WEBGL\_multi\_draw.multiDrawArraysInstancedWEBGL()
==================================================

The `WEBGL_multi_draw.multiDrawArraysInstancedWEBGL()` method of the [WebGL API](../webgl_api) renders multiple primitives from array data. It is identical to multiple calls to the [`gl.drawArraysInstanced()`](../webgl2renderingcontext/drawarraysinstanced) method.

Syntax
------

    void ext.multiDrawArraysWEBGL(mode,
        firstsList, firstsOffset,
        countsList, countsOffset,
        instanceCountsList, instanceCountsOffset,
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

`firstsList`  
An [`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array) or [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) (of [`GLint`](../webgl_api/types)) specifying a list of starting indices for the arrays of vector points.

`firstsOffset`  
A [`GLuint`](../webgl_api/types) defining the starting point into the `firstsLists` array.

`countsList`  
An [`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array) or [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) (of [`GLsizei`](../webgl_api/types)) specifying a list of numbers of indices to be rendered.

`countsOffset`  
A [`GLuint`](../webgl_api/types) defining the starting point into the `countsList` array.

`instanceCountsList`  
An [`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array) or [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) (of [`GLsizei`](../webgl_api/types)) specifying a list of number sof instances of the range of elements to execute.

`instanceCountsOffset`  
A [`GLuint`](../webgl_api/types) defining the starting point into the `instanceCountsList` array.

`drawCount`  
A [`GLsizei`](../webgl_api/types) specifying the number of instances of the range of elements to execute.

### Return value

None.

### Exceptions

-   If `mode` is not one of the accepted values, a `gl.INVALID_ENUM` error is thrown.
-   If `drawCount` or items in `firstsList`, `countsList`, or `instanceCountsList` are negative, a `gl.INVALID_VALUE` error is thrown.
-   if `gl.CURRENT_PROGRAM` is [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null), a `gl.INVALID_OPERATION` error is thrown.

Examples
--------

    // let firsts = new Int32Array(...);
    // let counts = new Int32Array(...);
    // let instanceCounts = new Int32Array(...);
    ext.multiDrawArraysInstancedWEBGL(
       gl.TRIANGLES, firsts, 0, counts, 0, instanceCounts, 0, firsts.length);

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

`multiDrawArraysInstancedWEBGL`

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

-   [`WebGLRenderingContext.drawArrays()`](../webglrenderingcontext/drawarrays)
-   [`WebGL2RenderingContext.drawArraysInstanced()`](../webgl2renderingcontext/drawarraysinstanced)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_multi_draw/multiDrawArraysInstancedWEBGL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_multi_draw/multiDrawArraysInstancedWEBGL</a>
