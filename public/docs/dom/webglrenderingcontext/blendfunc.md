WebGLRenderingContext.blendFunc()
=================================

The `WebGLRenderingContext.blendFunc()` method of the [WebGL API](../webgl_api) defines which function is used for blending pixel arithmetic.

Syntax
------

    void gl.blendFunc(sfactor, dfactor);

### Parameters

`sfactor`  
A [`GLenum`](../webgl_api/types) specifying a multiplier for the source blending factors. The default value is `gl.ONE`. For possible values, see below.

`dfactor`  
A [`GLenum`](../webgl_api/types) specifying a multiplier for the destination blending factors. The default value is `gl.ZERO`. For possible values, see below.

### Return value

None.

### Exceptions

-   If *sfactor* or *dfactor* is not one of the listed possible values, a `gl.INVALID_ENUM` error is thrown.
-   If a constant color and a constant alpha value are used together as source and destination factors, a `gl.INVALID_ENUM` error is thrown.

Constants
---------

The following constants can be used for *sfactor* and *dfactor*.

The formula for the blending color can be described like this: color(RGBA) = (sourceColor \* *sfactor*) + (destinationColor \* *dfactor*). The RBGA values are between 0 and 1.

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Constant</th><th>Factor</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>gl.ZERO</code></td><td>0,0,0,0</td><td>Multiplies all colors by 0.</td></tr><tr class="even"><td><code>gl.ONE</code></td><td>1,1,1,1</td><td>Multiplies all colors by 1.</td></tr><tr class="odd"><td><code>gl.SRC_COLOR</code></td><td>R<sub>S</sub>, G<sub>S</sub>, B<sub>S</sub>, A<sub>S</sub></td><td>Multiplies all colors by the source colors.</td></tr><tr class="even"><td><code>gl.ONE_MINUS_SRC_COLOR</code></td><td>1-R<sub>S</sub>, 1-G<sub>S</sub>, 1-B<sub>S</sub>, 1-A<sub>S</sub></td><td>Multiplies all colors by 1 minus each source color.</td></tr><tr class="odd"><td><code>gl.DST_COLOR</code></td><td>R<sub>D</sub>, G<sub>D</sub>, B<sub>D</sub>, A<sub>D</sub></td><td>Multiplies all colors by the destination color.</td></tr><tr class="even"><td><code>gl.ONE_MINUS_DST_COLOR</code></td><td>1-R<sub>D</sub>, 1-G<sub>D</sub>, 1-B<sub>D</sub>, 1-A<sub>D</sub></td><td>Multiplies all colors by 1 minus each destination color.</td></tr><tr class="odd"><td><code>gl.SRC_ALPHA</code></td><td>A<sub>S</sub>, A<sub>S</sub>, A<sub>S</sub>, A<sub>S</sub></td><td>Multiplies all colors by the source alpha value.</td></tr><tr class="even"><td><code>gl.ONE_MINUS_SRC_ALPHA</code></td><td>1-A<sub>S</sub>, 1-A<sub>S</sub>, 1-A<sub>S</sub>, 1-A<sub>S</sub></td><td>Multiplies all colors by 1 minus the source alpha value.</td></tr><tr class="odd"><td><code>gl.DST_ALPHA</code></td><td>A<sub>D</sub>, A<sub>D</sub>, A<sub>D</sub>, A<sub>D</sub></td><td>Multiplies all colors by the destination alpha value.</td></tr><tr class="even"><td><code>gl.ONE_MINUS_DST_ALPHA</code></td><td>1-A<sub>D</sub>, 1-A<sub>D</sub>, 1-A<sub>D</sub>, 1-A<sub>D</sub></td><td>Multiplies all colors by 1 minus the destination alpha value.</td></tr><tr class="odd"><td><code>gl.CONSTANT_COLOR</code></td><td>R<sub>C</sub>, G<sub>C</sub>, B<sub>C</sub>, A<sub>C</sub></td><td>Multiplies all colors by a constant color.</td></tr><tr class="even"><td><code>gl.ONE_MINUS_CONSTANT_COLOR</code></td><td>1-R<sub>C</sub>, 1-G<sub>C</sub>, 1-B<sub>C</sub>, 1-A<sub>C</sub></td><td>Multiplies all colors by 1 minus a constant color.</td></tr><tr class="odd"><td><code>gl.CONSTANT_ALPHA</code></td><td>A<sub>C</sub>, A<sub>C</sub>, A<sub>C</sub>, A<sub>C</sub></td><td>Multiplies all colors by a constant alpha value.</td></tr><tr class="even"><td><code>gl.ONE_MINUS_CONSTANT_ALPHA</code></td><td>1-A<sub>C</sub>, 1-A<sub>C</sub>, 1-A<sub>C</sub>, 1-A<sub>C</sub></td><td>Multiplies all colors by 1 minus a constant alpha value.</td></tr><tr class="odd"><td><code>gl.SRC_ALPHA_SATURATE</code></td><td><p>min(A<sub>S</sub>, 1 - A<sub>D</sub>), min(A<sub>S</sub>, 1 - A<sub>D</sub>), min(A<sub>S</sub>, 1 - A<sub>D</sub>), 1</p></td><td>Multiplies the RGB colors by the smaller of either the source alpha value or the value of 1 minus the destination alpha value. The alpha value is multiplied by 1.</td></tr></tbody></table>

Examples
--------

To use the blend function, you first have to activate blending with [`WebGLRenderingContext.enable()`](enable) with the argument `gl.BLEND`.

    gl.enable(gl.BLEND);
    gl.blendFunc(gl.SRC_COLOR, gl.DST_COLOR);

To get the current blend function, query the `BLEND_SRC_RGB`, `BLEND_SRC_ALPHA`, `BLEND_DST_RGB`, and `BLEND_DST_ALPHA` constants which return one of the blend function constants.

    gl.enable(gl.BLEND);
    gl.blendFunc(gl.SRC_COLOR, gl.DST_COLOR);
    gl.getParameter(gl.BLEND_SRC_RGB) == gl.SRC_COLOR;
    // true

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'blendFunc' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.<br />
In WebGL, constant color and constant alpha cannot be used together as source and destination factors in the blend function. See section 6.13. of the specification.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glBlendFunc.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glBlendFunc' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`blendFunc`

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

-   [`WebGLRenderingContext.blendColor()`](blendcolor)
-   [`WebGLRenderingContext.blendEquation()`](blendequation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/blendFunc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/blendFunc</a>
