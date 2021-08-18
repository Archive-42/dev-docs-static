WebGLRenderingContext.isEnabled()
=================================

The `WebGLRenderingContext.isEnabled()` method of the [WebGL API](../webgl_api) tests whether a specific WebGL capability is enabled or not for this context.

By default, all capabilities except `gl.DITHER` are **disabled**.

Syntax
------

    GLboolean gl.isEnabled(cap);

### Parameters

`cap`  
A [`GLenum`](../webgl_api/types) specifying which WebGL capability to test. Possible values:

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>gl.BLEND</code></td><td>Blending of the computed fragment color values. See <a href="blendfunc"><code>WebGLRenderingContext.blendFunc()</code></a>.</td></tr><tr class="even"><td><code>gl.CULL_FACE</code></td><td>Culling of polygons. See <a href="cullface"><code>WebGLRenderingContext.cullFace()</code></a>.</td></tr><tr class="odd"><td><code>gl.DEPTH_TEST</code></td><td>Depth comparisons and updates to the depth buffer. See <a href="depthfunc"><code>WebGLRenderingContext.depthFunc()</code></a>.</td></tr><tr class="even"><td><code>gl.DITHER</code></td><td>Dithering of color components before they get written to the color buffer.</td></tr><tr class="odd"><td><code>gl.POLYGON_OFFSET_FILL</code></td><td>Adding an offset to depth values of polygon's fragments. See <a href="polygonoffset"><code>WebGLRenderingContext.polygonOffset()</code></a>.</td></tr><tr class="even"><td><code>gl.SAMPLE_ALPHA_TO_COVERAGE</code></td><td>Computation of a temporary coverage value determined by the alpha value.</td></tr><tr class="odd"><td><code>gl.SAMPLE_COVERAGE</code></td><td>ANDing the fragment's coverage with the temporary coverage value. See <a href="samplecoverage"><code>WebGLRenderingContext.sampleCoverage()</code></a>.</td></tr><tr class="even"><td><code>gl.SCISSOR_TEST</code></td><td>Scissor test that discards fragments that are outside of the scissor rectangle. See <a href="scissor"><code>WebGLRenderingContext.scissor()</code></a>.</td></tr><tr class="odd"><td><code>gl.STENCIL_TEST</code></td><td>Stencil testing and updates to the stencil buffer. See <a href="stencilfunc"><code>WebGLRenderingContext.stencilFunc()</code></a>.</td></tr></tbody></table>

When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>gl.RASTERIZER_DISCARD</code></td><td>Primitives are discarded immediately before the rasterization stage, but after the optional transform feedback stage. <code>gl.clear()</code> commands are ignored.</td></tr></tbody></table>

### Return value

A [`GLboolean`](../webgl_api/types) indicating if the capability *cap* is enabled (`true`), or not (`false`).

Examples
--------

    gl.isEnabled(gl.STENCIL_TEST);
    // false

To activate or deactivate a specific capability, use the [`WebGLRenderingContext.enable()`](enable) and [`WebGLRenderingContext.disable()`](disable) methods:

    gl.enable(gl.STENCIL_TEST);
    gl.disable(gl.STENCIL_TEST);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'isEnabled' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glIsEnabled.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glIsEnabled' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 2.0 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.2">WebGL 2.0<br />
<span class="small">The definition of 'isEnabled' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Updated definition for WebGL 2.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glIsEnabled.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glIsEnabled' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3.0 API.</td></tr></tbody></table>

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

`isEnabled`

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

-   [`WebGLRenderingContext.enable()`](enable)
-   [`WebGLRenderingContext.disable()`](disable)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/isEnabled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/isEnabled</a>
