WebGLRenderingContext.getUniform()
==================================

The `WebGLRenderingContext.getUniform()` method of the [WebGL API](../webgl_api) returns the value of a uniform variable at a given location.

Syntax
------

    any gl.getUniform(program, location);

### Parameters

program  
A [`WebGLProgram`](../webglprogram) containing the uniform attribute.

location  
A [`WebGLUniformLocation`](../webgluniformlocation) object containing the location of the uniform attribute to get.

### Return value

The returned type depends on the uniform type:

Uniform type

Returned type

WebGL 1 only

`boolean`

[`GLBoolean`](../webgl_api/types)

`int`

[`GLint`](../webgl_api/types)

`float`

[`GLfloat`](../webgl_api/types)

`vec2`

[`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) (with 2 elements)

`ivec2`

[`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array) (with 2 elements)

`bvec2`

[`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLBoolean`](../webgl_api/types) (with 2 elements)

`vec3`

[`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) (with 3 elements)

`ivec3`

[`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array) (with 3 elements)

`bvec3`

[`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLBoolean`](../webgl_api/types) (with 3 elements)

`vec4`

[`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) (with 4 elements)

`ivec4`

[`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array) (with 4 elements)

`bvec4`

[`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`GLBoolean`](../webgl_api/types) (with 4 elements)

`mat2`

[`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) (with 4 elements)

`mat3`

[`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) (with 9 elements)

`mat4`

[`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) (with 16 elements)

`sampler2D`

[`GLint`](../webgl_api/types)

`samplerCube`

[`GLint`](../webgl_api/types)

Additionally available in WebGL 2

`uint`

[`GLuint`](../webgl_api/types)

`uvec2`

[`Uint32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint32Array) (with 2 elements)

`uvec3`

[`Uint32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint32Array) (with 3 elements)

`uvec4`

[`Uint32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint32Array) (with 4 elements)

`mat2x3`

[`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) (with 6 elements)

`mat2x4`

[`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) (with 8 elements)

`mat3x2`

[`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) (with 6 elements)

`mat3x4`

[`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) (with 12 elements)

`mat4x2`

[`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) (with 8 elements)

`mat4x3`

[`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) (with 12 elements)

any sampler type

[`GLint`](../webgl_api/types)

Examples
--------

    var loc = gl.getUniformLocation(program, 'u_foobar');
    gl.getUniform(program, loc);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.10">WebGL 1.0<br />
<span class="small">The definition of 'getUniform' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetUniform.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetUniform' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 2 API.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.8">WebGL 2.0<br />
<span class="small">The definition of 'getUniform' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Updated definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetUniform.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetUniform' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL ES 3 API.</td></tr></tbody></table>

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

`getUniform`

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

-   [`WebGLUniformLocation`](../webgluniformlocation)
-   [`WebGLRenderingContext.getActiveUniform()`](getactiveuniform)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getUniform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getUniform</a>
