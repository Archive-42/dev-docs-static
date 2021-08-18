WebGLRenderingContext.disable()
===============================

The `WebGLRenderingContext.disable()` method of the [WebGL API](../webgl_api) disables specific WebGL capabilities for this context.

Syntax
------

    void gl.disable(cap);

### Parameters

`cap`  
A [`GLenum`](../webgl_api/types) specifying which WebGL capability to disable. Possible values:

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>gl.BLEND</code></td><td>Deactivates blending of the computed fragment color values. See <a href="blendfunc"><code>WebGLRenderingContext.blendFunc()</code></a>.</td></tr><tr class="even"><td><code>gl.CULL_FACE</code></td><td>Deactivates culling of polygons. See <a href="cullface"><code>WebGLRenderingContext.cullFace()</code></a>.</td></tr><tr class="odd"><td><code>gl.DEPTH_TEST</code></td><td>Deactivates depth comparisons and updates to the depth buffer. See <a href="depthfunc"><code>WebGLRenderingContext.depthFunc()</code></a>.</td></tr><tr class="even"><td><code>gl.DITHER</code></td><td>Deactivates dithering of color components before they get written to the color buffer.</td></tr><tr class="odd"><td><code>gl.POLYGON_OFFSET_FILL</code></td><td>Deactivates adding an offset to depth values of polygon's fragments. See <a href="polygonoffset"><code>WebGLRenderingContext.polygonOffset()</code></a>.</td></tr><tr class="even"><td><code>gl.SAMPLE_ALPHA_TO_COVERAGE</code></td><td>Deactivates the computation of a temporary coverage value determined by the alpha value.</td></tr><tr class="odd"><td><code>gl.SAMPLE_COVERAGE</code></td><td>Deactivates ANDing the fragment's coverage with the temporary coverage value. See <a href="samplecoverage"><code>WebGLRenderingContext.sampleCoverage()</code></a>.</td></tr><tr class="even"><td><code>gl.SCISSOR_TEST</code></td><td>Deactivates the scissor test that discards fragments that are outside of the scissor rectangle. See <a href="scissor"><code>WebGLRenderingContext.scissor()</code></a>.</td></tr><tr class="odd"><td><code>gl.STENCIL_TEST</code></td><td>Deactivates stencil testing and updates to the stencil buffer. See <a href="stencilfunc"><code>WebGLRenderingContext.stencilFunc()</code></a>.</td></tr></tbody></table>

When using a [WebGL 2 context](../webgl2renderingcontext), the following values are available additionally:

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>gl.RASTERIZER_DISCARD</code></td><td>Deactivates that primitives are discarded immediately before the rasterization stage, but after the optional transform feedback stage. <code>gl.clear()</code> commands are ignored.</td></tr></tbody></table>

### Return value

None.

Examples
--------

    gl.disable(gl.DITHER);

To check if a capability is disabled, use the [`WebGLRenderingContext.isEnabled()`](isenabled) method:

    gl.isEnabled(gl.DITHER);
    // false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'disable' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glDisable.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glDisable' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 2.0 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glEnable.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glDisable' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3.0 API.</td></tr></tbody></table>

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

`disable`

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
-   [`WebGLRenderingContext.isEnabled()`](isenabled)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/disable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/disable</a>
