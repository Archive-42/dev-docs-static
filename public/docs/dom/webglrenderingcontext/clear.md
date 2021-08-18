WebGLRenderingContext.clear()
=============================

The `WebGLRenderingContext.clear()` method of the [WebGL API](../webgl_api) clears buffers to preset values.

The preset values can be set by [`clearColor()`](clearcolor), [`clearDepth()`](cleardepth) or [`clearStencil()`](clearstencil).

The scissor box, dithering, and buffer writemasks can affect the `clear()` method.

Syntax
------

    void gl.clear(mask);

### Parameters

`mask`  
A [`GLbitfield`](../webgl_api/types) bitwise OR mask that indicates the buffers to be cleared. Possible values are:

-   `gl.COLOR_BUFFER_BIT`
-   `gl.DEPTH_BUFFER_BIT`
-   `gl.STENCIL_BUFFER_BIT`

### Return value

None.

### Exceptions

If *mask* is not one of the listed possible values, a `gl.INVALID_ENUM` error is thrown.

Examples
--------

The `clear()` method accepts multiple values.

    gl.clear(gl.DEPTH_BUFFER_BIT);
    gl.clear(gl.DEPTH_BUFFER_BIT | gl.COLOR_BUFFER_BIT);

To get the current clear values, query the `COLOR_CLEAR_VALUE`, `DEPTH_CLEAR_VALUE`, and `STENCIL_CLEAR_VALUE` constants.

    gl.getParameter(gl.COLOR_CLEAR_VALUE);
    gl.getParameter(gl.DEPTH_CLEAR_VALUE);
    gl.getParameter(gl.STENCIL_CLEAR_VALUE);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.11">WebGL 1.0<br />
<span class="small">The definition of 'clear' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glClear.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glClear' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`clear`

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

-   [`WebGLRenderingContext.clearColor()`](clearcolor)
-   [`WebGLRenderingContext.clearDepth()`](cleardepth)
-   [`WebGLRenderingContext.clearStencil()`](clearstencil)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/clear" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/clear</a>
