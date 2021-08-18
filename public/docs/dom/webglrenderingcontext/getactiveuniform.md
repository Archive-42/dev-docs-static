WebGLRenderingContext.getActiveUniform()
========================================

The `WebGLRenderingContext.getActiveUniform()` method of the [WebGL API](../webgl_api) returns a [`WebGLActiveInfo`](../webglactiveinfo) object containing size, type, and name of a uniform attribute. It is generally used when querying unknown uniforms either for debugging or generic library creation.

Syntax
------

    WebGLActiveInfo WebGLRenderingContext.getActiveUniform(program, index);

### Parameters

`program`  
A [`WebGLProgram`](../webglprogram) specifying the WebGL shader program from which to obtain the uniform variable's information.

`index`  
A [`GLuint`](../webgl_api/types) specifying the index of the uniform attribute to get. This value is an index 0 to N - 1 as returned by [`gl.getProgramParameter(program, gl.ACTIVE_UNIFORMS)`](getprogramparameter).

### Return value

A [`WebGLActiveInfo`](../webglactiveinfo) object describing the uniform.

The `type` attribute of the return value will be one of the following:

-   `gl.FLOAT`
-   `gl.FLOAT_VEC2`
-   `gl.FLOAT_VEC3`
-   `gl.FLOAT_VEC4`
-   `gl.INT`
-   `gl.INT_VEC2`
-   `gl.INT_VEC3`
-   `gl.INT_VEC4`
-   `gl.BOOL`
-   `gl.BOOL_VEC2`
-   `gl.BOOL_VEC3`
-   `gl.BOOL_VEC4`
-   `gl.FLOAT_MAT2`
-   `gl.FLOAT_MAT3`
-   `gl.FLOAT_MAT4`
-   `gl.SAMPLER_2D`
-   `gl.SAMPLER_CUBE`
-   When using a [WebGL 2 context](../webgl2renderingcontext), the following values are possible additionally:
    -   `gl.UNSIGNED_INT`
    -   `gl.UNSIGNED_INT_VEC2`
    -   `gl.UNSIGNED_INT_VEC3`
    -   `gl.UNSIGNED_INT_VEC4`
    -   `gl.FLOAT_MAT2x3`
    -   `gl.FLOAT_MAT2x4`
    -   `gl.FLOAT_MAT3x2`
    -   `gl.FLOAT_MAT3x4`
    -   `gl.FLOAT_MAT4x2`
    -   `gl.FLOAT_MAT4x3`
    -   `gl.SAMPLER_3D`
    -   `gl.SAMPLER_2D_SHADOW`
    -   `gl.SAMPLER_2D_ARRAY`
    -   `gl.SAMPLER_2D_ARRAY_SHADOW`
    -   `gl.SAMPLER_CUBE_SHADOW`
    -   `gl.INT_SAMPLER_2D`
    -   `gl.INT_SAMPLER_3D`
    -   `gl.INT_SAMPLER_CUBE`
    -   `gl.INT_SAMPLER_2D_ARRAY`
    -   `gl.UNSIGNED_INT_SAMPLER_2D`
    -   `gl.UNSIGNED_INT_SAMPLER_3D`
    -   `gl.UNSIGNED_INT_SAMPLER_CUBE`
    -   `gl.UNSIGNED_INT_SAMPLER_2D_ARRAY`

When `gl.linkProgram` is called, WebGL creates a list of active uniforms. These are possible values of the `name` attribute of return values of [`getActiveUniform`](getactiveuniform). WebGL generates one or more entries in the list depending on the declared type of the uniform in the shader:

-   Single basic type: one entry with the name of the uniform. E.g. `uniform vec4 a;` will result in `a`.
-   Array of basic type: one entry with the name of the uniform suffixed with `[0]`. E.g. `uniform vec4 b[];` will result in `b[0]`.
-   Struct type: one entry for each member of the struct. E.g. `uniform struct { float foo; vec4 bar; } c;` will result in `c.foo` and `c.bar`.
-   Arrays of structs or arrays: each entry of the array will generate its own entries. E.g. `uniform struct { float foo; vec4 bar; } d[2];` will result in:
    -   `d[0].foo`
    -   `d[0].bar`
    -   `d[1].foo`
    -   `d[1].bar`
-   Uniform blocks: one entry for each member. If the uniform block has an instance name, the block name is prefixed. E.g. `uniform Block { float foo; };` will result in `foo`, and `uniform Block { float bar; } e;` will result in `Block.bar`.

The `size` attribute of the return value corresponds to the length of the array for uniforms declared as arrays. Otherwise, it is 1 (this includes interface blocks instanced with arrays).

### Exceptions

-   `gl.INVALID_VALUE` is generated if the program [`WebGLProgram`](../webglprogram) is invalid (not linked, deleted, etc.).
-   `gl.INVALID_VALUE` is generated if index is not in the range \[0, `gl.getProgramParameter(program, gl.ACTIVE_UNIFORMS)` - 1\].

Examples
--------

    const numUniforms = gl.getProgramParameter(program, gl.ACTIVE_UNIFORMS);
    for (let i = 0; i < numUniforms; ++i) {
      const info = gl.getActiveUniform(program, i);
      console.log('name:', info.name, 'type:', info.type, 'size:', info.size);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.10">WebGL 1.0<br />
<span class="small">The definition of 'getActiveUniform' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetActiveUniform.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetActiveUniform' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`getActiveUniform`

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

-   [`WebGLActiveInfo`](../webglactiveinfo)
-   [`WebGLRenderingContext.getUniformLocation()`](getuniformlocation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getActiveUniform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getActiveUniform</a>
