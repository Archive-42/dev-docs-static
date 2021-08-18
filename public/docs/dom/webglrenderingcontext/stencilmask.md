WebGLRenderingContext.stencilMask()
===================================

The `WebGLRenderingContext.stencilMask()` method of the [WebGL API](../webgl_api) controls enabling and disabling of both the front and back writing of individual bits in the stencil planes.

The [`WebGLRenderingContext.stencilMaskSeparate()`](stencilmaskseparate) method can set front and back stencil writemasks to different values.

Syntax
------

    void gl.stencilMask(mask);

### Parameters

`mask`  
A [`GLuint`](../webgl_api/types) specifying a bit mask to enable or disable writing of individual bits in the stencil planes. By default, the mask is all 1.

### Return value

None.

Examples
--------

    gl.stencilMask(110101);

To get the current stencil masks, query the `STENCIL_WRITEMASK`, `STENCIL_BACK_WRITEMASK`, or `STENCIL_BITS` constants.

    gl.getParameter(gl.STENCIL_WRITEMASK);
    // 110101
    gl.getParameter(gl.STENCIL_BACK_WRITEMASK);
    // 110101
    gl.getParameter(gl.STENCIL_BITS);
    // 0

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'stencilMask' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glStencilMask.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glStencilMask' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`stencilMask`

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

-   [`WebGLRenderingContext.colorMask()`](colormask)
-   [`WebGLRenderingContext.depthMask()`](depthmask)
-   [`WebGLRenderingContext.stencilMaskSeparate()`](stencilmaskseparate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/stencilMask" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/stencilMask</a>
