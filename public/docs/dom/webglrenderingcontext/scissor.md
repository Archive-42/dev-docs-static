WebGLRenderingContext.scissor()
===============================

The `WebGLRenderingContext.scissor()` method of the [WebGL API](../webgl_api) sets a scissor box, which limits the drawing to a specified rectangle.

Syntax
------

    void gl.scissor(x, y, width, height);

### Parameters

`x`  
A [`GLint`](../webgl_api/types) specifying the horizontal coordinate for the lower left corner of the box. Default value: 0.

`y`  
A [`GLint`](../webgl_api/types) specifying the vertical coordinate for the lower left corner of the box. Default value: 0.

width  
A non-negative [`Glsizei`](../webgl_api/types) specifying the width of the scissor box. Default value: width of the canvas.

height  
A non-negative [`Glsizei`](../webgl_api/types) specifying the height of the scissor box. Default value: height of the canvas.

### Return value

None.

### Exceptions

If either *width* or *height* is a negative value, a `gl.INVALID_VALUE` error is thrown.

Examples
--------

When the scissor test is enabled, only pixels within the scissor box can be modified by drawing commands.

    // turn on scissor test
    gl.enable(gl.SCISSOR_TEST);

    // set the scissor rectangle
    gl.scissor(x, y, width, height);

    // execute drawing commands in the scissor box (e.g. clear)

    // turn off scissor test again
    gl.disable(gl.SCISSOR_TEST);

To get the current scissor box dimensions, query the `SCISSOR_BOX` constant which returns an [`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array).

    gl.scissor(0, 0, 200, 200);
    gl.getParameter(gl.SCISSOR_BOX);
    // Int32Array[0, 0, 200, 200]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.4">WebGL 1.0<br />
<span class="small">The definition of 'scissor' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glScissor.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glScissor' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`scissor`

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

-   [`WebGLRenderingContext.viewport()`](viewport)
-   [`WebGLRenderingContext.enable()`](enable)
-   [`WebGLRenderingContext.disable()`](disable)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/scissor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/scissor</a>
