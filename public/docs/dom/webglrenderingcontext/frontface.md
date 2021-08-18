WebGLRenderingContext.frontFace()
=================================

The `WebGLRenderingContext.frontFace()` method of the [WebGL API](../webgl_api) specifies whether polygons are front- or back-facing by setting a winding orientation.

Syntax
------

    void gl.frontFace(mode);

### Parameters

mode  
A [GLenum](../webgl_api/types) type winding orientation. The default value is `gl.CCW`. Possible values:

-   `gl.CW`: Clock-wise winding.
-   `gl.CCW`: Counter-clock-wise winding.

### Return value

None.

Examples
--------

    gl.frontFace(gl.CW);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'frontFace' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glFrontFace.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glFrontFace' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`frontFace`

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

-   [`WebGLRenderingContext.cullFace()`](cullface)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/frontFace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/frontFace</a>
