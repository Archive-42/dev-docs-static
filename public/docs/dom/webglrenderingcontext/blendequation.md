WebGLRenderingContext.blendEquation()
=====================================

The `WebGLRenderingContext.blendEquation()` method of the [WebGL API](../webgl_api) is used to set both the RGB blend equation and alpha blend equation to a single equation.

The blend equation determines how a new pixel is combined with a pixel already in the [`WebGLFramebuffer`](../webglframebuffer).

Syntax
------

    void gl.blendEquation(mode);

### Parameters

`mode`  
A [`GLenum`](../webgl_api/types) specifying how source and destination colors are combined. Must be either:

-   `gl.FUNC_ADD`: source + destination,
-   `gl.FUNC_SUBTRACT`: source - destination,
-   `gl.FUNC_REVERSE_SUBTRACT`: destination - source
-   When using the [`EXT_blend_minmax`](../ext_blend_minmax) extension:
    -   `ext.MIN_EXT`: Minimum of source and destination,
    -   `ext.MAX_EXT`: Maximum of source and destination.
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:
    -   `gl.MIN`: Minimum of source and destination,
    -   `gl.MAX`: Maximum of source and destination.

**default value**: `gl.FUNC_ADD`

### Exception

If *mode* is not one of the three possible values, a `gl.INVALID_ENUM` error is thrown.

### Return value

None.

Examples
--------

To set the blend equation, use:

    gl.blendEquation(gl.FUNC_ADD);
    gl.blendEquation(gl.FUNC_SUBTRACT);
    gl.blendEquation(gl.FUNC_REVERSE_SUBTRACT);

To get the blend equations, query the `BLEND_EQUATION`, `BLEND_EQUATION_RGB` and `BLEND_EQUATION_ALPHA` constants which return `gl.FUNC_ADD`, `gl.FUNC_SUBTRACT`, `gl.FUNC_REVERSE_SUBTRACT`, or if the [`EXT_blend_minmax`](../ext_blend_minmax) is enabled: `ext.MIN_EXT` or `ext.MAX_EXT`.

    gl.getParameter(gl.BLEND_EQUATION_RGB) === gl.FUNC_ADD;
    // true

    gl.getParameter(gl.BLEND_EQUATION_ALPHA) === gl.FUNC_ADD;
    // true

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'blendEquation' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glBlendEquation.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glBlendEquation' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL ES 2.0 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glBlendEquation.xml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glBlendEquation' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL ES 3.0 API.</td></tr></tbody></table>

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

`blendEquation`

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

`WebGL2`

56

79

51

No

43

No

58

58

51

43

No

7.0

See also
--------

-   [`WebGLRenderingContext.blendColor()`](blendcolor)
-   [`WebGLRenderingContext.blendFunc()`](blendfunc)
-   [`EXT_blend_minmax`](../ext_blend_minmax)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/blendEquation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/blendEquation</a>
