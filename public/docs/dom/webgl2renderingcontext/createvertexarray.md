WebGL2RenderingContext.createVertexArray()
==========================================

The `WebGL2RenderingContext.createVertexArray()` method of the [WebGL 2 API](../webgl_api) creates and initializes a [`WebGLVertexArrayObject`](../webglvertexarrayobject) object that represents a vertex array object (VAO) pointing to vertex array data and which provides names for different sets of vertex data.

Syntax
------

    WebGLVertexArrayObject gl.createVertexArray();

### Parameters

None.

### Return value

A [`WebGLVertexArrayObject`](../webglvertexarrayobject) representing a vertex array object (VAO) which points to vertex array data.

Examples
--------

    var vao = gl.createVertexArray();
    gl.bindVertexArray(vao);

    // ...
    // calls to bindBuffer or vertexAttribPointer
    // which will be "recorded" in the VAO
    // ...

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.17">WebGL 2.0<br />
<span class="small">The definition of 'createVertexArray' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGenVertexArrays.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGenVertexArrays' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`createVertexArray`

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

-   [`WebGLVertexArrayObject`](../webglvertexarrayobject)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/createVertexArray" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/createVertexArray</a>
