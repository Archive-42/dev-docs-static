# ANGLE_instanced_arrays.drawArraysInstancedANGLE()

The `ANGLE_instanced_arrays.drawArraysInstancedANGLE()` method of the [WebGL API](../webgl_api) renders primitives from array data like the [`gl.drawArrays()`](../webglrenderingcontext/drawarrays) method. In addition, it can execute multiple instances of the range of elements.

**Note:** When using [`WebGL2`](../webgl2renderingcontext), this method is available as [`gl.drawArraysInstanced()`](../webgl2renderingcontext/drawarraysinstanced) by default.

## Syntax

    void ext.drawArraysInstancedANGLE(mode, first, count, primcount);

### Parameters

`mode`  
A [`GLenum`](../webgl_api/types) specifying the type primitive to render. Possible values are:

- `gl.POINTS`: Draws a single dot.
- `gl.LINE_STRIP`: Draws a straight line to the next vertex.
- `gl.LINE_LOOP`: Draws a straight line to the next vertex, and connects the last vertex back to the first.
- `gl.LINES`: Draws a line between a pair of vertices.
- `gl.TRIANGLE_STRIP`
- `gl.TRIANGLE_FAN`
- `gl.TRIANGLES`: Draws a triangle for a group of three vertices.

first  
A [`GLint`](../webgl_api/types) specifying the starting index in the array of vector points.

count  
A [`GLsizei`](../webgl_api/types) specifying the number of indices to be rendered.

primcount  
A [`GLsizei`](../webgl_api/types) specifying the number of instances of the range of elements to execute.

### Return value

None.

### Exceptions

- If `mode` is not one of the accepted values, a `gl.INVALID_ENUM` error is thrown.
- If `first`, `count` or `primcount` are negative, a `gl.INVALID_VALUE` error is thrown.
- if `gl.CURRENT_PROGRAM` is [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null), a `gl.INVALID_OPERATION` error is thrown.

## Examples

    var ext = gl.getExtension('ANGLE_instanced_arrays');
    ext.drawArraysInstancedANGLE(gl.POINTS, 0, 8, 4);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/ANGLE_instanced_arrays/">ANGLE_instanced_arrays<br />
<span class="small">The definition of 'ANGLE_instanced_arrays' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`drawArraysInstancedANGLE`

32

12

47

11

19

8

4.4

32

Yes

19

8

2.0

## See also

- [`ext.drawElementsInstancedANGLE()`](drawelementsinstancedangle)
- [`ext.vertexAttribDivisorANGLE()`](vertexattribdivisorangle)
- [`WebGLRenderingContext.drawArrays()`](../webglrenderingcontext/drawarrays)
- [`WebGLRenderingContext.drawElements()`](../webglrenderingcontext/drawelements)
- [`WebGL2RenderingContext.drawArraysInstanced()`](../webgl2renderingcontext/drawarraysinstanced)
- [`WebGL2RenderingContext.drawElementsInstanced()`](../webgl2renderingcontext/drawelementsinstanced)
- [`WebGL2RenderingContext.vertexAttribDivisor()`](../webgl2renderingcontext/vertexattribdivisor)
- [`WEBGL_multi_draw.multiDrawArraysInstancedWEBGL()`](../webgl_multi_draw/multidrawarraysinstancedwebgl)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ANGLE_instanced_arrays/drawArraysInstancedANGLE" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ANGLE_instanced_arrays/drawArraysInstancedANGLE</a>
