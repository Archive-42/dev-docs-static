WebGLRenderingContext.lineWidth()
=================================

The `WebGLRenderingContext.lineWidth()` method of the [WebGL API](../webgl_api) sets the line width of rasterized lines.

The webgl spec, based on the OpenGL ES 2.0/3.0 specs points out that the minimum and maximum width for a line is implementation defined. The maximum minimum width is allowed to be 1.0. The minimum maximum width is also allowed to be 1.0. Because of these implementation defined limits it is not recommended to use line widths other than 1.0 since there is no guarantee any user's browser will display any other width.

As of January 2017 most implementations of WebGL only support a minimum of 1 and a maximum of 1 as the technology they are based on has these same limits.

Syntax
------

    void gl.lineWidth(width);

### Parameters

width  
A [`GLfloat`](../webgl_api/types) specifying the width of rasterized lines. Default value: 1.

### Return value

None.

Examples
--------

Setting the line width:

    gl.lineWidth(5);

Getting the line width:

    gl.getParameter(gl.LINE_WIDTH);

Getting the range of available widths. Returns a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array).

    gl.getParameter(gl.ALIASED_LINE_WIDTH_RANGE);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'lineWidth' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glLineWidth.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glLineWidth' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`lineWidth`

No

12-79

No

11

No

No

No

No

No

No

No

No

See also
--------

-   [`WebGLRenderingContext`](../webglrenderingcontext)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/lineWidth" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/lineWidth</a>
