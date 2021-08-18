WebGLRenderingContext.stencilFunc()
===================================

The `WebGLRenderingContext.stencilFunc()` method of the [WebGL API](../webgl_api) sets the front and back function and reference value for stencil testing.

Stenciling enables and disables drawing on a per-pixel basis. It is typically used in multipass rendering to achieve special effects.

Syntax
------

    void gl.stencilFunc(func, ref, mask);

### Parameters

`func`  
A [`GLenum`](../webgl_api/types) specifying the test function. The default function is `gl.ALWAYS`. The possible values are:

-   `gl.NEVER`: Never pass.
-   `gl.LESS`: Pass if `(ref & mask) <  (stencil & mask)`.
-   `gl.EQUAL`: Pass if `(ref & mask) =  (stencil & mask)`.
-   `gl.LEQUAL`: Pass if `(ref & mask) <= (stencil & mask)`.
-   `gl.GREATER`: Pass if `(ref & mask) >  (stencil & mask)`.
-   `gl.NOTEQUAL`: Pass if `(ref & mask) != (stencil & mask)`.
-   `gl.GEQUAL`: Pass if `(ref & mask) >= (stencil & mask)`.
-   `gl.ALWAYS`: Always pass.

`ref`  
A [`GLint`](../webgl_api/types) specifying the reference value for the stencil test. This value is clamped to the range 0 to 2<sup>n</sup> -1 where n is the number of bitplanes in the stencil buffer. The default value is 0.

`mask`  
A [`GLuint`](../webgl_api/types) specifying a bit-wise mask that is used to AND the reference value and the stored stencil value when the test is done. The default value is all 1.

### Return value

None.

Examples
--------

The stencil testing is disabled by default. To enable or disable stencil testing, use the [`enable()`](enable) and [`disable()`](disable) methods with the argument `gl.STENCIL_TEST`.

    gl.enable(gl.STENCIL_TEST);
    gl.stencilFunc(gl.LESS, 0, 0b1110011);

To get the current stencil function, reference value, or other stencil information, query the following constants with [`getParameter()`](getparameter).

    gl.getParameter(gl.STENCIL_FUNC);
    gl.getParameter(gl.STENCIL_VALUE_MASK);
    gl.getParameter(gl.STENCIL_REF);
    gl.getParameter(gl.STENCIL_BACK_FUNC);
    gl.getParameter(gl.STENCIL_BACK_VALUE_MASK);
    gl.getParameter(gl.STENCIL_BACK_REF);
    gl.getParameter(gl.STENCIL_BITS);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'stencilFunc' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glStencilFunc.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glStencilFunc' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`stencilFunc`

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

-   [`WebGLRenderingContext.stencilFuncSeparate()`](stencilfuncseparate)
-   [`WebGLRenderingContext.stencilMask()`](stencilmask)
-   [`WebGLRenderingContext.stencilMaskSeparate()`](stencilmaskseparate)
-   [`WebGLRenderingContext.stencilOp()`](stencilop)
-   [`WebGLRenderingContext.stencilOpSeparate()`](stencilopseparate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/stencilFunc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/stencilFunc</a>
