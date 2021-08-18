WebGL2RenderingContext.vertexAttribI4\[u\]i\[v\]()
==================================================

The `WebGL2RenderingContext.vertexAttribI4[u]i[v]()` methods of the [WebGL 2 API](../webgl_api) specify integer values for generic vertex attributes.

Syntax
------

    void gl.vertexAttribI4i(index, v0, v1, v2, v3);
    void gl.vertexAttribI4ui(index, v0, v1, v2, v3);

    void gl.vertexAttribI4iv(index, value);
    void gl.vertexAttribI4uiv(index, value);

### Parameters

`index`  
A [`GLuint`](../webgl_api/types) specifying the position of the vertex attribute to be modified.

`v0, v1, v2, v3`  
An integer [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) for the vertex attribute value.

`value`  
A [`Uint32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint32Array)/[`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array) or sequences of [`GLuint`](../webgl_api/types)/ [`GLint`](../webgl_api/types) for integer vector vertex attribute values.

### Return value

None.

Examples
--------

    gl.vertexAttribI4i(a_foobar, 10);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.8">WebGL 2.0<br />
<span class="small">The definition of 'vertexAttribI' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition for WebGL.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glVertexAttrib.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glVertexAttribI' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`vertexAttribI`

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

-   [`WebGLRenderingContext.getVertexAttrib()`](../webglrenderingcontext/getvertexattrib)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/vertexAttribI" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/vertexAttribI</a>
