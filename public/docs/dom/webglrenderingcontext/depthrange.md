WebGLRenderingContext.depthRange()
==================================

The `WebGLRenderingContext.depthRange()` method of the [WebGL API](../webgl_api) specifies the depth range mapping from normalized device coordinates to window or viewport coordinates.

Syntax
------

    void gl.depthRange(zNear, zFar);

### Parameters

`zNear`  
A [`GLclampf`](../webgl_api/types) specifying the mapping of the near clipping plane to window or viewport coordinates. Clamped to the range 0 to 1 and must be less than or equal to `zFar`. The default value i`s 0.`

`zFar`  
A [`GLclampf`](../webgl_api/types) specifying the mapping of the far clipping plane to window or viewport coordinates. Clamped to the range 0 to 1. The default value i`s 1.`

### Return value

None.

Examples
--------

    gl.depthRange(0.2, 0.6);

To check the current depth range, query the `DEPTH_RANGE` constant which returns a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array)

    gl.getParameter(gl.DEPTH_RANGE);
    // Float32Array[0.2, 0.6]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'depthRange' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition. Unlike OpenGL, WebGL requires <code>zNear</code> and <code>zFar</code> values to be clamped to the range 0 to 1. Additionally, <code>zNear</code> must be less than or equal to <code>zFar</code>.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glDepthRangef.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glDepthRangef' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`depthRange`

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
-   [`WebGLRenderingContext.depthFunc()`](depthfunc)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/depthRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/depthRange</a>
