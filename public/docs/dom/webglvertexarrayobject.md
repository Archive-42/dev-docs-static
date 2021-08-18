WebGLVertexArrayObject
======================

The `WebGLVertexArrayObject` interface is part of the [WebGL 2 API](webgl_api), represents vertex array objects (VAOs) pointing to vertex array data, and provides names for different sets of vertex data.

When working with `WebGLVertexArrayObject` objects, the following methods are useful:

-   [`WebGL2RenderingContext.createVertexArray()`](webgl2renderingcontext/createvertexarray)
-   [`WebGL2RenderingContext.deleteVertexArray()`](webgl2renderingcontext/deletevertexarray)
-   [`WebGL2RenderingContext.isVertexArray()`](webgl2renderingcontext/isvertexarray)
-   [`WebGL2RenderingContext.bindVertexArray()`](webgl2renderingcontext/bindvertexarray)

**WebGL 1:** The [`OES_vertex_array_object`](oes_vertex_array_object) extension allows you to use vertex array objects in a WebGL 1 context.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.6">WebGL 2.0<br />
<span class="small">The definition of 'WebGLVertexArrayObject' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WebGLVertexArrayObject`

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

-   [`OES_vertex_array_object`](oes_vertex_array_object)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLVertexArrayObject" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLVertexArrayObject</a>
