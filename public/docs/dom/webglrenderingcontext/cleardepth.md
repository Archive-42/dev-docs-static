WebGLRenderingContext.clearDepth()
==================================

The `WebGLRenderingContext.clearDepth()` method of the [WebGL API](../webgl_api) specifies the clear value for the depth buffer.

This specifies what depth value to use when calling the [`clear()`](clear) method. The value is clamped between 0 and 1.

Syntax
------

    void gl.clearDepth(depth);

### Parameters

`depth`  
A [`GLclampf`](../webgl_api/types) specifying the depth value used when the depth buffer is cleared. Default value: 1.

### Return value

None.

Examples
--------

    gl.clearDepth(0.5);

To get the current depth clear value, query the `DEPTH_CLEAR_VALUE` constant.

    gl.getParameter(gl.DEPTH_CLEAR_VALUE);
    // 0.5

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'clearDepth' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glClearDepthf.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glClearDepthf' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`clearDepth`

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
-   [`WebGLRenderingContext.clearStencil()`](clearstencil)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/clearDepth" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/clearDepth</a>
