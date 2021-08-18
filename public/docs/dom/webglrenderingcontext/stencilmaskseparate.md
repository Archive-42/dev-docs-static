WebGLRenderingContext.stencilMaskSeparate()
===========================================

The `WebGLRenderingContext.stencilMaskSeparate()` method of the [WebGL API](../webgl_api) controls enabling and disabling of front and/or back writing of individual bits in the stencil planes.

The [`WebGLRenderingContext.stencilMask()`](stencilmask) method can set both, the front and back stencil writemasks to one value at the same time.

Syntax
------

    void gl.stencilMaskSeparate(face, mask);

### Parameters

face  
A [`GLenum`](../webgl_api/types) specifying whether the front and/or back stencil writemask is updated. The possible values are:

-   `gl.FRONT`
-   `gl.BACK`
-   `gl.FRONT_AND_BACK`

`mask`  
A [`GLuint`](../webgl_api/types) specifying a bit mask to enable or disable writing of individual bits in the stencil planes. By default, the mask is all 1.

### Return value

None.

Examples
--------

    gl.stencilMaskSeparate(gl.FRONT, 110101);

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
<span class="small">The definition of 'stencilMaskSeparate' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glStencilMaskSeparate.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glStencilMaskSeparate' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`stencilMaskSeparate`

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
-   [`WebGLRenderingContext.stencilMask()`](stencilmask)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/stencilMaskSeparate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/stencilMaskSeparate</a>
