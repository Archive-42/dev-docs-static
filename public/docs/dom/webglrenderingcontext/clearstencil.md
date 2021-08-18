WebGLRenderingContext.clearStencil()
====================================

The `WebGLRenderingContext.clearStencil()` method of the [WebGL API](../webgl_api) specifies the clear value for the stencil buffer.

This specifies what stencil value to use when calling the [`clear()`](clear) method.

Syntax
------

    void gl.clearStencil(s);

### Parameters

`s`  
A [`GLint`](../webgl_api/types) specifying the index used when the stencil buffer is cleared. Default value: 0.

### Return value

None.

Examples
--------

    gl.clearStencil(1);

To get the current stencil clear value, query the `STENCIL_CLEAR_VALUE` constant.

    gl.getParameter(gl.STENCIL_CLEAR_VALUE);
    // 1

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'clearStencil' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glClearStencil.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glClearStencil' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`clearStencil`

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

-   [`WebGLRenderingContext.clear()`](clear)
-   [`WebGLRenderingContext.clearColor()`](clearcolor)
-   [`WebGLRenderingContext.clearDepth()`](cleardepth)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/clearStencil" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/clearStencil</a>
