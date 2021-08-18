WebGL2RenderingContext.getSamplerParameter()
============================================

The `WebGL2RenderingContext.getSamplerParameter()` method of the [WebGL 2 API](../webgl_api) returns parameter information of a [`WebGLSampler`](../webglsampler) object.

Syntax
------

    any gl.getSamplerParameter(sampler, pname);

### Parameters

sampler  
A [`WebGLSampler`](../webglsampler) object.

`pname`  
A [`GLenum`](../webgl_api/types) specifying which information to return. Possible values:

-   `gl.TEXTURE_COMPARE_FUNC`: Returns a [`GLenum`](../webgl_api/types) indicating the texture comparison function.
-   `gl.TEXTURE_COMPARE_MODE`: Returns a [`GLenum`](../webgl_api/types) indicating the texture comparison mode.
-   `gl.TEXTURE_MAG_FILTER`: Returns a [`GLenum`](../webgl_api/types) indicating the texture magnification filter.
-   `gl.TEXTURE_MAX_LOD`: Returns a [`GLfloat`](../webgl_api/types) indicating the maximum level-of-detail value.
-   `gl.TEXTURE_MIN_FILTER`: Returns a [`GLenum`](../webgl_api/types) indicating the texture minification filter
-   `gl.TEXTURE_MIN_LOD`: Returns a [`GLfloat`](../webgl_api/types) indicating the minimum level-of-detail value.
-   `gl.TEXTURE_WRAP_R`: Returns a [`GLenum`](../webgl_api/types) indicating the texture wrapping function for the texture coordinate r.
-   `gl.TEXTURE_WRAP_S`: Returns a [`GLenum`](../webgl_api/types) indicating the texture wrapping function for the texture coordinate s.
-   `gl.TEXTURE_WRAP_T`: Returns a [`GLenum`](../webgl_api/types) indicating the texture wrapping function for the texture coordinate t.

### Return value

Depends on the `pname` parameter, either a [`GLenum`](../webgl_api/types) or a [`GLfloat`](../webgl_api/types).

Examples
--------

    var sampler = gl.createSampler();
    gl.getSamplerParameter(sampler, gl.TEXTURE_COMPARE_FUNC);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.13">WebGL 2.0<br />
<span class="small">The definition of 'getSamplerParameter' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetSamplerParameter.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetSamplerParameter' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`getSamplerParameter`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getSamplerParameter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getSamplerParameter</a>
