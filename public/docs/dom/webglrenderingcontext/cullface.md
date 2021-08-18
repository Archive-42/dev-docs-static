WebGLRenderingContext.cullFace()
================================

The `WebGLRenderingContext.cullFace()` method of the [WebGL API](../webgl_api) specifies whether or not front- and/or back-facing polygons can be culled.

Syntax
------

    void gl.cullFace(mode);

### Parameters

`mode`  
A [`GLenum`](../webgl_api/types) specifying whether front- or back-facing polygons are candidates for culling. The default value is `gl.BACK`. Possible values are:

-   `gl.FRONT`
-   `gl.BACK`
-   `gl.FRONT_AND_BACK`

### Return value

None.

Examples
--------

Polygon culling is disabled by default. To enable or disable culling, use the [`enable()`](enable) and [`disable()`](disable) methods with the argument `gl.CULL_FACE`.

    gl.enable(gl.CULL_FACE);
    gl.cullFace(gl.FRONT_AND_BACK);

To check the current cull face mode, query the `CULL_FACE_MODE` constant.

    gl.getParameter(gl.CULL_FACE_MODE) === gl.FRONT_AND_BACK;
    // true

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'cullFace' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glCullFace.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glCullFace' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`cullFace`

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

-   [`WebGLRenderingContext.enable()`](enable)
-   [`WebGLRenderingContext.frontFace()`](frontface)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/cullFace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/cullFace</a>
