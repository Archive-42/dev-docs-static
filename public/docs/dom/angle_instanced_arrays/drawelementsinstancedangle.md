# ANGLE_instanced_arrays.drawElementsInstancedANGLE()

The `ANGLE_instanced_arrays.drawElementsInstancedANGLE()` method of the [WebGL API](../webgl_api) renders primitives from array data like the [`gl.drawElements()`](../webglrenderingcontext/drawelements) method. In addition, it can execute multiple instances of a set of elements.

**Note:** When using [`WebGL2`](../webgl2renderingcontext), this method is available as [`gl.drawElementsInstanced()`](../webgl2renderingcontext/drawelementsinstanced) by default.

## Syntax

    void ext.drawElementsInstancedANGLE(mode, count, type, offset, primcount);

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

count  
A [`GLsizei`](../webgl_api/types) specifying the number of elements to be rendered.

type  
A [`GLenum`](../webgl_api/types) specifying the type of the values in the element array buffer. Possible values are:

- `gl.UNSIGNED_BYTE`
- `gl.UNSIGNED_SHORT`
- When using the [`OES_element_index_uint`](../oes_element_index_uint) extension:
  - `gl.UNSIGNED_INT`

offset  
A [`GLintptr`](../webgl_api/types) specifying an offset in the element array buffer. Must be a valid multiple of the size of the given `type`.

primcount  
A [`GLsizei`](../webgl_api/types) specifying the number of instances of the set of elements to execute.

### Return value

None.

### Exceptions

- If `mode` is not one of the accepted values, a `gl.INVALID_ENUM` error is thrown.
- If `offset` is a invalid multiple of the size of the given type, a `gl.INVALID_OPERATION` error is thrown.
- If `count` or `primcount` are negative, a `gl.INVALID_VALUE` error is thrown.

## Examples

    var ext = gl.getExtension('ANGLE_instanced_arrays');
    ext.drawElementsInstancedANGLE(gl.POINTS, 2, gl.UNSIGNED_SHORT, 0, 4);

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

`drawElementsInstancedANGLE`

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

- [`ext.drawArraysInstancedANGLE()`](drawarraysinstancedangle)
- [`ext.vertexAttribDivisorANGLE()`](vertexattribdivisorangle)
- [`WebGLRenderingContext.drawArrays()`](../webglrenderingcontext/drawarrays)
- [`WebGLRenderingContext.drawElements()`](../webglrenderingcontext/drawelements)
- [`WebGL2RenderingContext.drawArraysInstanced()`](../webgl2renderingcontext/drawarraysinstanced)
- [`WebGL2RenderingContext.drawElementsInstanced()`](../webgl2renderingcontext/drawelementsinstanced)
- [`WebGL2RenderingContext.vertexAttribDivisor()`](../webgl2renderingcontext/vertexattribdivisor)
- [`WEBGL_multi_draw.multiDrawElementsInstancedWEBGL()`](../webgl_multi_draw/multidrawelementsinstancedwebgl)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ANGLE_instanced_arrays/drawElementsInstancedANGLE" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ANGLE_instanced_arrays/drawElementsInstancedANGLE</a>
