# ANGLE_instanced_arrays

The `ANGLE_instanced_arrays` extension is part of the [WebGL API](webgl_api) and allows to draw the same object, or groups of similar objects multiple times, if they share the same vertex data, primitive count and type.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is only available to [WebGL1](webglrenderingcontext) contexts. In [WebGL2](webgl2renderingcontext), the functionality of this extension is available on the WebGL2 context by default and the constants and methods are available without the "`ANGLE`" suffix.

Despite the name "ANGLE", this extension works on any device if the hardware supports it and not just on Windows when using the ANGLE library. "ANGLE" just indicates that this extension has been written by the ANGLE library authors.

## Constants

This extension exposes one new constant, which can be used in the [`gl.getVertexAttrib()`](webglrenderingcontext/getvertexattrib) method:

`ext.VERTEX_ATTRIB_ARRAY_DIVISOR_ANGLE`  
Returns a [`GLint`](webgl_api/types) describing the frequency divisor used for instanced rendering when used in the [`gl.getVertexAttrib()`](webglrenderingcontext/getvertexattrib) as the `pname` parameter.

## Methods

This extension exposes three new methods.

[`ext.drawArraysInstancedANGLE()`](angle_instanced_arrays/drawarraysinstancedangle)  
Behaves identically to [`gl.drawArrays()`](webglrenderingcontext/drawarrays) except that multiple instances of the range of elements are executed, and the instance advances for each iteration.

[`ext.drawElementsInstancedANGLE()`](angle_instanced_arrays/drawelementsinstancedangle)  
Behaves identically to [`gl.drawElements()`](webglrenderingcontext/drawelements) except that multiple instances of the set of elements are executed and the instance advances between each set.

[`ext.vertexAttribDivisorANGLE()`](angle_instanced_arrays/vertexattribdivisorangle)  
Modifies the rate at which generic vertex attributes advance when rendering multiple instances of primitives with [`ext.drawArraysInstancedANGLE()`](angle_instanced_arrays/drawarraysinstancedangle) and [`ext.drawElementsInstancedANGLE()`](angle_instanced_arrays/drawelementsinstancedangle).

## Examples

Enabling the extension:

    var ext = gl.getExtension('ANGLE_instanced_arrays');

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

`ANGLE_instanced_arrays`

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

- [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
- [`WebGL2RenderingContext.drawArraysInstanced()`](webgl2renderingcontext/drawarraysinstanced)
- [`WebGL2RenderingContext.drawElementsInstanced()`](webgl2renderingcontext/drawelementsinstanced)
- [`WebGL2RenderingContext.vertexAttribDivisor()`](webgl2renderingcontext/vertexattribdivisor)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ANGLE_instanced_arrays" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ANGLE_instanced_arrays</a>
