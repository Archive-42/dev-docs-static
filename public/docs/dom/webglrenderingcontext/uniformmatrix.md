WebGLRenderingContext.uniformMatrix\[234\]fv()
==============================================

The `WebGLRenderingContext.uniformMatrix[234]fv()` methods of the [WebGL API](../webgl_api) specify matrix values for uniform variables.

The three versions of this method (`uniformMatrix2fv()`, `uniformMatrix3fv()`, and `uniformMatrix4fv()`) take as the input value 2-component, 3-component, and 4-component square matrices, respectively. They are expected to have 4, 9 or 16 floats.

Syntax
------

    WebGLRenderingContext.uniformMatrix2fv(location, transpose, value);
    WebGLRenderingContext.uniformMatrix3fv(location, transpose, value);
    WebGLRenderingContext.uniformMatrix4fv(location, transpose, value);

### Parameters

`location`  
A [`WebGLUniformLocation`](../webgluniformlocation) object containing the location of the uniform attribute to modify. The location is obtained using [`getUniformLocation()`](getuniformlocation).

`transpose`  
A [`GLboolean`](../webgl_api/types) specifying whether to transpose the matrix. Must be `false`.

`value`  
A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) or sequence of `GLfloat` values. The values are assumed to be supplied in column major order.

### Return value

`undefined`

Examples
--------

    gl.uniformMatrix2fv(loc, false, [2,1, 2,2]);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.10">WebGL 1.0<br />
<span class="small">The definition of 'uniformMatrix' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glUniform.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glUniform' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`uniformMatrix`

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

-   [`WebGLRenderingContext.uniform()`](uniform)
-   [`WebGL2RenderingContext.uniformMatrix()`](../webgl2renderingcontext/uniformmatrix) – WebGL 2 versions of these methods.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/uniformMatrix" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/uniformMatrix</a>
