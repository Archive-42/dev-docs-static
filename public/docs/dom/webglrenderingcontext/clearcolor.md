WebGLRenderingContext.clearColor()
==================================

The `WebGLRenderingContext.clearColor()` method of the [WebGL API](../webgl_api) specifies the color values used when clearing color buffers.

This specifies what color values to use when calling the [`clear()`](clear) method. The values are clamped between 0 and 1.

Syntax
------

    void gl.clearColor(red, green, blue, alpha);

### Parameters

`red`  
A [`GLclampf`](../webgl_api/types) specifying the red color value used when the color buffers are cleared. Default value: 0.

`green`  
A [`GLclampf`](../webgl_api/types) specifying the green color value used when the color buffers are cleared. Default value: 0.

`blue`  
A [`GLclampf`](../webgl_api/types) specifying the blue color value used when the color buffers are cleared. Default value: 0.

`alpha`  
A [`GLclampf`](../webgl_api/types) specifying the alpha (transparency) value used when the color buffers are cleared. Default value: 0.

### Return value

None.

Examples
--------

    gl.clearColor(1, 0.5, 0.5, 3);

To get the current clear color, query the `COLOR_CLEAR_VALUE` constant which returns a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array).

    gl.getParameter(gl.COLOR_CLEAR_VALUE);
    // Float32Array[1, 0.5, 0.5, 1]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'clearColor' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glClearColor.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glClearColor' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`clearColor`

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
-   [`WebGLRenderingContext.clearDepth()`](cleardepth)
-   [`WebGLRenderingContext.clearStencil()`](clearstencil)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/clearColor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/clearColor</a>
