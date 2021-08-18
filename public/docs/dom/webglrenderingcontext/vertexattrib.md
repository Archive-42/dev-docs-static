WebGLRenderingContext.vertexAttrib\[1234\]f\[v\]()
==================================================

The `WebGLRenderingContext.vertexAttrib[1234]f[v]()` methods of the [WebGL API](../webgl_api) specify constant values for generic vertex attributes.

Syntax
------

    void gl.vertexAttrib1f(index, v0);
    void gl.vertexAttrib2f(index, v0, v1);
    void gl.vertexAttrib3f(index, v0, v1, v2);
    void gl.vertexAttrib4f(index, v0, v1, v2, v3);

    void gl.vertexAttrib1fv(index, value);
    void gl.vertexAttrib2fv(index, value);
    void gl.vertexAttrib3fv(index, value);
    void gl.vertexAttrib4fv(index, value);

### Parameters

`index`  
A [`GLuint`](../webgl_api/types) specifying the position of the vertex attribute to be modified.

`v0, v1, v2, v3`  
A floating point [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) for the vertex attribute value.

`value`  
A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) for floating point vector vertex attribute values.

### Return value

None.

Description
-----------

While vertex attributes are usually used to specify values which are different for each vertex (using [`vertexAttribPointer`](vertexattribpointer)), it can be useful to specify a constant value. For example, if you have a shader which has a `color` vertex attribute, but you want to draw everything in a single color, you can use `vertexAttrib` to achieve that without creating a buffer filled with only one value or having to create a separate shader which uses a uniform for the color.

This value will be used if a bound array buffer has not been enabled with [`enableVertexAttribArray`](enablevertexattribarray).

Attributes may be matrices, in which case columns of the matrix must be loaded into successive vertex attribute slots.

The values set with [`vertexAttribPointer`](vertexattribpointer) are context-global, i.e. they aren't part of the shader state (like generix vertex attribute indexes to shader variable bindings) and aren't part of the vertex array object state (like enabled vertex attribute arrays). The only way to change the values is by calling this function again.

Examples
--------

    const a_foobar = gl.getAttribLocation(shaderProgram, 'foobar');
    //either set each component individually:
    gl.vertexAttrib3f(a_foobar, 10.0, 5.0, 2.0);
    //or provide a Float32Array:
    const floatArray = new Float32Array([10.0, 5.0, 2.0]);
    gl.vertexAttrib3fv(a_foobar, floatArray);

    // we want to load the following 3x3 matrix into attribute named "matrix3x3"
    // 0 1 2
    // 3 4 5
    // 6 7 8
    const matrix3x3Location = gl.getAttribLocation(shaderProgram, 'matrix3x3');
    gl.vertexAttrib3f(matrix3x3Location,     0, 3, 6);
    gl.vertexAttrib3f(matrix3x3Location + 1, 1, 4, 7);
    gl.vertexAttrib3f(matrix3x3Location + 2, 2, 5, 8);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.10">WebGL 1.0<br />
<span class="small">The definition of 'vertexAttrib' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glVertexAttrib.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glVertexAttrib' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`vertexAttrib`

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

-   [`WebGLRenderingContext.getVertexAttrib()`](getvertexattrib)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/vertexAttrib" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/vertexAttrib</a>
