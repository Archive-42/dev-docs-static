# ANGLE_instanced_arrays.vertexAttribDivisorANGLE()

The **ANGLE_instanced_arrays.vertexAttribDivisorANGLE()** method of the [WebGL API](../webgl_api) modifies the rate at which generic vertex attributes advance when rendering multiple instances of primitives with [`ext.drawArraysInstancedANGLE()`](drawarraysinstancedangle) and [`ext.drawElementsInstancedANGLE()`](drawelementsinstancedangle).

**Note:** When using [`WebGL2`](../webgl2renderingcontext), this method is available as [`gl.vertexAttribDivisor()`](../webgl2renderingcontext/vertexattribdivisor) by default.

## Syntax

    void ext.vertexAttribDivisorANGLE(index, divisor);

### Parameters

`index`  
A [`GLuint`](../webgl_api/types) specifying the index of the generic vertex attributes.

`divisor`  
A [`GLuint`](../webgl_api/types) specifying the number of instances that will pass between updates of the generic attribute.

### Return value

None.

## Examples

    var ext = gl.getExtension('ANGLE_instanced_arrays');
    ext.vertexAttribDivisorANGLE(0, 2);

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

`vertexAttribDivisorANGLE`

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
- [`ext.drawElementsInstancedANGLE()`](drawelementsinstancedangle)
- [`WebGLRenderingContext.drawArrays()`](../webglrenderingcontext/drawarrays)
- [`WebGLRenderingContext.drawElements()`](../webglrenderingcontext/drawelements)
- [`WebGL2RenderingContext.drawArraysInstanced()`](../webgl2renderingcontext/drawarraysinstanced)
- [`WebGL2RenderingContext.drawElementsInstanced()`](../webgl2renderingcontext/drawelementsinstanced)
- [`WebGL2RenderingContext.vertexAttribDivisor()`](../webgl2renderingcontext/vertexattribdivisor)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ANGLE_instanced_arrays/vertexAttribDivisorANGLE" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ANGLE_instanced_arrays/vertexAttribDivisorANGLE</a>
