WebGLRenderingContext.colorMask()
=================================

The `WebGLRenderingContext.colorMask()` method of the [WebGL API](../webgl_api) sets which color components to enable or to disable when drawing or rendering to a [`WebGLFramebuffer`](../webglframebuffer).

Syntax
------

    void gl.colorMask(red, green, blue, alpha);

### Parameters

`red`  
A [`GLboolean`](../webgl_api/types) specifying whether or not the red color component can be written into the frame buffer. Default value: `true`.

`green`  
A [`GLboolean`](../webgl_api/types) specifying whether or not the green color component can be written into the frame buffer. Default value: `true`.

`blue`  
A [`GLboolean`](../webgl_api/types) specifying whether or not the blue color component can be written into the frame buffer. Default value: `true`.

`alpha`  
A [`GLboolean`](../webgl_api/types) specifying whether or not the alpha (transparency) component can be written into the frame buffer. Default value: `true`.

### Return value

None.

Examples
--------

    gl.colorMask(true, true, true, false);

To get the current color mask, query the `COLOR_WRITEMASK` constant which returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array).

    gl.getParameter(gl.COLOR_WRITEMASK);
    // [true, true, true, false]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'colorMask' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glColorMask.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glColorMask' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`colorMask`

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

-   [`WebGLRenderingContext.depthMask()`](depthmask)
-   [`WebGLRenderingContext.stencilMask()`](stencilmask)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/colorMask" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/colorMask</a>
