WebGLRenderingContext.polygonOffset()
=====================================

The `WebGLRenderingContext.polygonOffset()` method of the [WebGL API](../webgl_api) specifies the scale factors and units to calculate depth values.

The offset is added before the depth test is performed and before the value is written into the depth buffer.

Syntax
------

    void gl.polygonOffset(factor, units);

### Parameters

factor  
A [`GLfloat`](../webgl_api/types) which sets the scale factor for the variable depth offset for each polygon. The default value is 0.

units  
A [`GLfloat`](../webgl_api/types) which sets the multiplier by which an implementation-specific value is multiplied with to create a constant depth offset. The default value is 0.

### Return value

None.

Examples
--------

The polygon offset fill is disabled by default. To enable or disable polygon offset fill, use the [`enable()`](enable) and [`disable()`](disable) methods with the argument `gl.POLYGON_OFFSET_FILL`.

    gl.enable(gl.POLYGON_OFFSET_FILL);
    gl.polygonOffset(2, 3);

To check the current polygon offset factor or units, query the `POLYGON_OFFSET_FACTOR` and `POLYGON_OFFSET_UNITS` constants.

    gl.getParameter(gl.POLYGON_OFFSET_FACTOR); // 2
    gl.getParameter(gl.POLYGON_OFFSET_UNITS);  // 3

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'polygonOffset' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glPolygonOffset.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glPolygonOffset' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`polygonOffset`

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

-   [`WebGLRenderingContext.depthFunc()`](depthfunc)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/polygonOffset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/polygonOffset</a>
