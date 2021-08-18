WebGL2RenderingContext.vertexAttribIPointer()
=============================================

The `WebGL2RenderingContext.vertexAttribIPointer()` method of the [WebGL 2 API](../webgl_api) specifies integer data formats and locations of vertex attributes in a vertex attributes array.

Syntax
------

    void gl.vertexAttribIPointer(index, size, type, stride, offset);

### Parameters

`index`  
A [`GLuint`](../webgl_api/types) specifying the index of the vertex attribute that is to be modified.

`size`  
A [`GLint`](../webgl_api/types) specifying the number of components per vertex attribute. Must be 1, 2, 3, or 4.

`type`  
A [`GLenum`](../webgl_api/types) specifying the data type of each component in the array. Must be one of: `gl.BYTE`, `gl.UNSIGNED_BYTE`, `gl.SHORT`, `gl.UNSIGNED_SHORT`, `gl.INT`, or `gl.UNSIGNED_INT`.

`stride`  
A [`GLsizei`](../webgl_api/types) specifying the offset in bytes between the beginning of consecutive vertex attributes.

`offset`  
A [`GLintptr`](../webgl_api/types) specifying an offset in bytes of the first component in the vertex attribute array. Must be a multiple of `type`.

### Return value

None.

Description
-----------

Very similar to [`WebGLRenderingContext.vertexAttribPointer()`](../webglrenderingcontext/vertexattribpointer). The main difference is that while values specified by `vertexAttribPointer` are always interpreted as floating-point values in the shader (even if they were originally specified as integers in the buffer), this method allows specifying values which are interpreted as integers in the shader.

Examples
--------

### Linear Blend Skinning

    //Describe the layout of the buffer:
    //1. position
    gl.vertexAttribPointer(0, 3, gl.FLOAT, false, 20, 0);
    gl.enableVertexAttribArray(0);
    //2. bone weights, normalized to [0, 1]
    gl.vertexAttribPointer(1, 4, gl.UNSIGNED_BYTE, true, 20, 12);
    gl.enableVertexAttribArray(1);
    //3. bone indices, interpreted as integer
    gl.vertexAttribIPointer(2, 4, gl.UNSIGNED_BYTE, 20, 16);
    gl.enableVertexAttribArray(2);

    //Connect to attributes from the vertex shader
    gl.bindAttribLocation(shaderProgram, 0, "position");
    gl.bindAttribLocation(shaderProgram, 1, "boneWeights");
    gl.bindAttribLocation(shaderProgram, 2, "boneIndices");

    <script id="shader-vs" type="x-shader/x-vertex">#version 300 es

    uniform mat4 mvMatrix;
    uniform mat4 bones[120];

    in vec3 position;
    in vec4 boneWeights;
    in uvec4 boneIndices;//read as 4-component unsigned integer

    void main() {
        vec4 skinnedPosition =
            bones[boneIndices.s] * vec4(position, 1.0) * boneWeights.s +
            bones[boneIndices.t] * vec4(position, 1.0) * boneWeights.t +
            bones[boneIndices.p] * vec4(position, 1.0) * boneWeights.p +
            bones[boneIndices.q] * vec4(position, 1.0) * boneWeights.q;
        gl_Position = mvMatrix * skinnedPosition;
    }
    </script>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.8">WebGL 2.0<br />
<span class="small">The definition of 'vertexAttribIPointer' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glVertexAttribPointer.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glVertexAttribPointer' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`vertexAttribIPointer`

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

-   [`WebGLRenderingContext.vertexAttribPointer()`](../webglrenderingcontext/vertexattribpointer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/vertexAttribIPointer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/vertexAttribIPointer</a>
