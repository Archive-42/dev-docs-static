WebGL2RenderingContext.deleteSampler()
======================================

The `WebGL2RenderingContext.deleteSampler()` method of the [WebGL 2 API](../webgl_api) deletes a given [`WebGLSampler`](../webglsampler) object.

Syntax
------

    void gl.deleteSampler(sampler);

### Parameters

`sampler`  
A [`WebGLSampler`](../webglsampler) object to delete.

### Return value

None.

Examples
--------

`gl` must be a [`WebGL2RenderingContext`](../webgl2renderingcontext). `WebGLSampler` objects are not available in WebGL 1.

    var sampler = gl.createSampler();

    // ...

    gl.deleteSampler(sampler);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.13">WebGL 2.0<br />
<span class="small">The definition of 'deleteSampler' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glDeleteSamplers.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glDeleteSamplers' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`deleteSampler`

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

-   [`WebGLSampler`](../webglsampler)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/deleteSampler" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/deleteSampler</a>
