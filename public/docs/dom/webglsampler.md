WebGLSampler
============

The `WebGLSampler` interface is part of the [WebGL 2](webgl_api) API and stores sampling parameters for [`WebGLTexture`](webgltexture) access inside of a shader.

When working with `WebGLSampler` objects, the following methods of the [`WebGL2RenderingContext`](webgl2renderingcontext) are useful:

-   [`WebGL2RenderingContext.createSampler()`](webgl2renderingcontext/createsampler)
-   [`WebGL2RenderingContext.deleteSampler()`](webgl2renderingcontext/deletesampler)
-   [`WebGL2RenderingContext.isSampler()`](webgl2renderingcontext/issampler)
-   [`WebGL2RenderingContext.bindSampler()`](webgl2renderingcontext/bindsampler)
-   [`WebGL2RenderingContext.getSamplerParameter()`](webgl2renderingcontext/getsamplerparameter)

Examples
--------

### Creating a `WebGLSampler` object

in this example, `gl` must be a [`WebGL2RenderingContext`](webgl2renderingcontext). `WebGLSampler` objects are not available in WebGL 1.

    var sampler = gl.createSampler();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.3">WebGL 2.0<br />
<span class="small">The definition of 'WebGLSample' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WebGLSampler`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLSampler" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLSampler</a>
