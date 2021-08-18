WebGLRenderingContext.stencilOpSeparate()
=========================================

The `WebGLRenderingContext.stencilOpSeparate()` method of the [WebGL API](../webgl_api) sets the front and/or back-facing stencil test actions.

Syntax
------

    void gl.stencilOpSeparate(face, fail, zfail, zpass);

### Parameters

The `fail`, `zfail` and `zpass` parameters accept all constants listed below.

face  
A [`GLenum`](../webgl_api/types) specifying whether the front and/or back stencil state is updated. The possible values are:

-   `gl.FRONT`
-   `gl.BACK`
-   `gl.FRONT_AND_BACK`

`fail`  
A [`GLenum`](../webgl_api/types) specifying the function to use when the stencil test fails. The default value is `gl.KEEP`.

`zfail`  
A [`GLenum`](../webgl_api/types) specifying the function to use when the stencil test passes, but the depth test fails. The default value is `gl.KEEP`.

`zpass`  
A [`GLenum`](../webgl_api/types) specifying the function to use when both the stencil test and the depth test pass, or when the stencil test passes and there is no depth buffer or depth testing is disabled. The default value is `gl.KEEP`.

### Return value

None.

Constants
---------

`gl.KEEP`  
Keeps the current value.

`gl.ZERO`  
Sets the stencil buffer value to 0.

`gl.REPLACE`  
Sets the stencil buffer value to the reference value as specified by [`WebGLRenderingContext.stencilFunc()`](stencilfunc).

`gl.INCR`  
Increments the current stencil buffer value. Clamps to the maximum representable unsigned value.

`gl.INCR_WRAP`  
Increments the current stencil buffer value. Wraps stencil buffer value to zero when incrementing the maximum representable unsigned value.

`gl.DECR`  
Decrements the current stencil buffer value. Clamps to 0.

`gl.DECR_WRAP`  
Decrements the current stencil buffer value. Wraps stencil buffer value to the maximum representable unsigned value when decrementing a stencil buffer value of 0.

`gl.INVERT`  
Inverts the current stencil buffer value bitwise.

Examples
--------

The stencil testing is disabled by default. To enable or disable stencil testing, use the [`enable()`](enable) and [`disable()`](disable) methods with the argument `gl.STENCIL_TEST`.

    gl.enable(gl.STENCIL_TEST);
    gl.stencilOpSeparate(gl.FRONT, gl.INCR, gl.DECR, gl.INVERT);

To get the current information about stencil and depth pass or fail, query the following constants with [`getParameter()`](getparameter).

    gl.getParameter(gl.STENCIL_FAIL);
    gl.getParameter(gl.STENCIL_PASS_DEPTH_PASS);
    gl.getParameter(gl.STENCIL_PASS_DEPTH_FAIL);
    gl.getParameter(gl.STENCIL_BACK_FAIL);
    gl.getParameter(gl.STENCIL_BACK_PASS_DEPTH_PASS);
    gl.getParameter(gl.STENCIL_BACK_PASS_DEPTH_FAIL);
    gl.getParameter(gl.STENCIL_BITS);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'stencilOpSeparate' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glStencilOpSeparate.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glStencilOpSeparate' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`stencilOpSeparate`

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

-   [`WebGLRenderingContext.stencilOp()`](stencilop)
-   [`WebGLRenderingContext.stencilFunc()`](stencilfunc)
-   [`WebGLRenderingContext.stencilFuncSeparate()`](stencilfuncseparate)
-   [`WebGLRenderingContext.stencilMask()`](stencilmask)
-   [`WebGLRenderingContext.stencilMaskSeparate()`](stencilmaskseparate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/stencilOpSeparate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/stencilOpSeparate</a>
