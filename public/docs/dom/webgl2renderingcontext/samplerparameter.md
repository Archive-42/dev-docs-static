WebGL2RenderingContext.samplerParameter\[if\]()
===============================================

The `WebGL2RenderingContext.samplerParameter[if]()` methods of the [WebGL 2 API](../webgl_api) set [`WebGLSampler`](../webglsampler) parameters.

Syntax
------

    void gl.samplerParameteri(sampler, pname, param);
    void gl.samplerParameterf(sampler, pname, param);

### Parameters

`sampler`  
A [`WebGLSampler`](../webglsampler) object.

`pname`  
A [`GLenum`](../webgl_api/types) specifying which parameter to set. Possible values:

-   `gl.TEXTURE_COMPARE_FUNC`: A [`GLenum`](../webgl_api/types) specifying the texture comparison function.
-   `gl.TEXTURE_COMPARE_MODE`: A [`GLenum`](../webgl_api/types) specifying the texture comparison mode.
-   `gl.TEXTURE_MAG_FILTER`: A [`GLenum`](../webgl_api/types) specifying the texture magnification filter.
-   `gl.TEXTURE_MAX_LOD`: A [`GLfloat`](../webgl_api/types) specifying the maximum level-of-detail value.
-   `gl.TEXTURE_MIN_FILTER`: A [`GLenum`](../webgl_api/types) specifying the texture minification filter
-   `gl.TEXTURE_MIN_LOD`: A [`GLfloat`](../webgl_api/types) specifying the minimum level-of-detail value.
-   `gl.TEXTURE_WRAP_R`: A [`GLenum`](../webgl_api/types) specifying the texture wrapping function for the texture coordinate r.
-   `gl.TEXTURE_WRAP_S`: A [`GLenum`](../webgl_api/types) specifying the texture wrapping function for the texture coordinate s.
-   `gl.TEXTURE_WRAP_T`: A [`GLenum`](../webgl_api/types) specifying the texture wrapping function for the texture coordinate t.

`param`  
A [`GLint`](../webgl_api/types) (`samplerParameteri`) or a [`GLfloat`](../webgl_api/types) (`samplerParameterf`) specifying a value for `pname`.

### Return value

None.

Examples
--------

    var sampler = gl.createSampler();
    gl.samplerParameteri(sampler, gl.TEXTURE_MAG_FILTER, gl.NEAREST);

Specifications
--------------

BCD tables only load in the browser

See also
--------

-   [`WebGLSampler`](../webglsampler)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/samplerParameter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/samplerParameter</a>
