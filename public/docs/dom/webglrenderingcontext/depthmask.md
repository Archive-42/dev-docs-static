WebGLRenderingContext.depthMask()
=================================

The `WebGLRenderingContext.depthMask()` method of the [WebGL API](../webgl_api) sets whether writing into the depth buffer is enabled or disabled.

Syntax
------

    void gl.depthMask(flag);

### Parameters

`flag`  
A [`GLboolean`](../webgl_api/types) specifying whether or not writing into the depth buffer is enabled. Default value: `true`, meaning that writing is enabled.

### Return value

None.

Examples
--------

    gl.depthMask(false);

To get the current depth mask, query the `DEPTH_WRITEMASK` constant which returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

    gl.getParameter(gl.DEPTH_WRITEMASK);
    // false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'depthMask' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glDepthMask.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glDepthMask' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`depthMask`

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
-   [`WebGLRenderingContext.stencilMask()`](stencilmask)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/depthMask" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/depthMask</a>
