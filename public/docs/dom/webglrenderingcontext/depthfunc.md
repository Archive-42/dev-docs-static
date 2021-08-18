WebGLRenderingContext.depthFunc()
=================================

The `WebGLRenderingContext.depthFunc()` method of the [WebGL API](../webgl_api) specifies a function that compares incoming pixel depth to the current depth buffer value.

Syntax
------

    void gl.depthFunc(func);

### Parameters

`func`  
A [`GLenum`](../webgl_api/types) specifying the depth comparison function, which sets the conditions under which the pixel will be drawn. The default value is `gl.LESS`. Possible values are:

-   `gl.NEVER` (never pass)
-   `gl.LESS` (pass if the incoming value is less than the depth buffer value)
-   `gl.EQUAL` (pass if the incoming value equals the depth buffer value)
-   `gl.LEQUAL` (pass if the incoming value is less than or equal to the depth buffer value)
-   `gl.GREATER` (pass if the incoming value is greater than the depth buffer value)
-   `gl.NOTEQUAL` (pass if the incoming value is not equal to the depth buffer value)
-   `gl.GEQUAL` (pass if the incoming value is greater than or equal to the depth buffer value)
-   `gl.ALWAYS` (always pass)

### Return value

None.

Examples
--------

The depth testing is disabled by default. To enable or disable depth testing, use the [`enable()`](enable) and [`disable()`](disable) methods with the argument `gl.DEPTH_TEST`.

    gl.enable(gl.DEPTH_TEST);
    gl.depthFunc(gl.NEVER);

To check the current depth function, query the `DEPTH_FUNC` constant.

    gl.getParameter(gl.DEPTH_FUNC) === gl.NEVER;
    // true

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'depthFunc' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glDepthFunc.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glDepthFunc' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`depthFunc`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/depthFunc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/depthFunc</a>
