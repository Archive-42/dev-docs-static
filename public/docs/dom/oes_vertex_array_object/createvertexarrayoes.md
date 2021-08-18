OES\_vertex\_array\_object.createVertexArrayOES()
=================================================

The `OES_vertex_array_object.createVertexArrayOES()` method of the [WebGL API](../webgl_api) creates and initializes a [`WebGLVertexArrayObject`](../webglvertexarrayobject) object that represents a vertex array object (VAO) pointing to vertex array data and which provides names for different sets of vertex data.

Syntax
------

    WebGLVertexArrayObjectOES ext.createVertexArrayOES();

### Parameters

None.

### Return value

A [`WebGLVertexArrayObject`](../webglvertexarrayobject) representing a vertex array object (VAO) which points to vertex array data.

Examples
--------

    var ext = gl.getExtension('OES_vertex_array_object');
    var vao = ext.createVertexArrayOES();
    ext.bindVertexArrayOES(vao);

    // ...
    // calls to bindBuffer or vertexAttribPointer
    // which will be "recorded" in the VAO
    // ...

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/OES_vertex_array_object/">OES_vertex_array_object<br />
<span class="small">The definition of 'OES_vertex_array_object' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`createVertexArrayOES`

24

17

25

No

15

8

≤37

25

?

14

8

1.5

See also
--------

-   [`WebGLRenderingContext.getExtension()`](../webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.vertexAttribPointer()`](../webglrenderingcontext/vertexattribpointer)
-   WebGL2 equivalent: [`WebGL2RenderingContext.createVertexArray()`](../webgl2renderingcontext/createvertexarray)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OES_vertex_array_object/createVertexArrayOES" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OES_vertex_array_object/createVertexArrayOES</a>
