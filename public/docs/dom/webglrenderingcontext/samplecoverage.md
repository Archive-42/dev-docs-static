WebGLRenderingContext.sampleCoverage()
======================================

The `WebGLRenderingContext.sampleCoverage()` method of the [WebGL API](../webgl_api) specifies multi-sample coverage parameters for anti-aliasing effects.

Syntax
------

    void gl.sampleCoverage(value, invert);

### Parameters

value  
A [`GLclampf`](../webgl_api/types) which sets a single floating-point coverage value clamped to the range \[0,1\]. The default value is 1.0.

invert  
A [`GLboolean`](../webgl_api/types) which sets whether or not the coverage masks should be inverted. The default value is `false`.

### Return value

None.

Examples
--------

Multi-sampling is disabled by default. To enable or disable multi-sampling, use the [`enable()`](enable) and [`disable()`](disable) methods with the argument `gl.SAMPLE_COVERAGE` and `gl.SAMPLE_ALPHA_TO_COVERAGE`.

    gl.enable(gl.SAMPLE_COVERAGE);
    gl.sampleCoverage(0.5, false);

To check the sample coverage values, query the `SAMPLE_COVERAGE_VALUE` and `SAMPLE_COVERAGE_INVERT` constants.

    gl.getParameter(gl.SAMPLE_COVERAGE_VALUE);  // 0.5
    gl.getParameter(gl.SAMPLE_COVERAGE_INVERT); // false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.3">WebGL 1.0<br />
<span class="small">The definition of 'sampleCoverage' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glSampleCoverage.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glSampleCoverage' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`sampleCoverage`

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

-   [`HTMLCanvasElement.getContext()`](../htmlcanvaselement/getcontext) – `antialias` parameter for the context.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/sampleCoverage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/sampleCoverage</a>
