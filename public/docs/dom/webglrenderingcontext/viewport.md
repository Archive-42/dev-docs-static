WebGLRenderingContext.viewport()
================================

The `WebGLRenderingContext.viewport()` method of the [WebGL API](../webgl_api) sets the viewport, which specifies the affine transformation of x and y from normalized device coordinates to window coordinates.

Syntax
------

    void gl.viewport(x, y, width, height);

### Parameters

`x`  
A [`GLint`](../webgl_api/types) specifying the horizontal coordinate for the lower left corner of the viewport origin. Default value: 0.

`y`  
A [`GLint`](../webgl_api/types) specifying the vertical coordinate for the lower left corner of the viewport origin. Default value: 0.

width  
A non-negative [`Glsizei`](../webgl_api/types) specifying the width of the viewport. Default value: width of the canvas.

height  
A non-negative [`Glsizei`](../webgl_api/types) specifying the height of the viewport. Default value: height of the canvas.

### Return value

None.

### Errors thrown

If either *width* or *height* is a negative value, a `gl.INVALID_VALUE` error is thrown.

Examples
--------

When you first create a WebGL context, the size of the viewport will match the size of the canvas. However, if you resize the canvas, you will need to tell the WebGL context a new viewport setting. In this situation, you can use `gl.viewport`.

    gl.viewport(0, 0, canvas.width, canvas.height);

The viewport width and height are clamped to a range that is implementation dependent. To get this range, you can use the `MAX_VIEWPORT_DIMS` constant, which returns an [`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array).

    gl.getParameter(gl.MAX_VIEWPORT_DIMS);
    // e.g. Int32Array[16384, 16384]

To get the current viewport, query the `VIEWPORT` constant.

    gl.getParameter(gl.VIEWPORT);
    // e.g. Int32Array[0, 0, 640, 480]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.4">WebGL 1.0<br />
<span class="small">The definition of 'viewport' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glViewport.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glViewport' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`viewport`

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

-   [`WebGLRenderingContext.scissor()`](scissor)
-   [`WebGLRenderingContext.getParameter()`](getparameter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/viewport" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/viewport</a>
