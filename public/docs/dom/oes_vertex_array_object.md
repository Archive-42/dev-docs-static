OES\_vertex\_array\_object
==========================

The **OES\_vertex\_array\_object** extension is part of the [WebGL API](webgl_api) and provides vertex array objects (VAOs) which encapsulate vertex array states. These objects keep pointers to vertex data and provide names for different sets of vertex data.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is only available to [WebGL1](webglrenderingcontext) contexts. In [WebGL2](webgl2renderingcontext), the functionality of this extension is available on the WebGL2 context by default and the constants and methods are available without the "`OES`" suffix.

Constants
---------

This extension exposes one new constant, which can be used in the [`gl.getParameter()`](webglrenderingcontext/getparameter) method:

`ext.VERTEX_ARRAY_BINDING_OES`  
Returns a [`WebGLVertexArrayObject`](webglvertexarrayobject) object when used in the [`gl.getParameter()`](webglrenderingcontext/getparameter) method as the `pname` parameter.

Methods
-------

This extension exposes four new methods.

[`ext.createVertexArrayOES()`](oes_vertex_array_object/createvertexarrayoes)  
Creates a new [`WebGLVertexArrayObject`](webglvertexarrayobject).

[`ext.deleteVertexArrayOES()`](oes_vertex_array_object/deletevertexarrayoes)  
Deletes a given [`WebGLVertexArrayObject`](webglvertexarrayobject).

[`ext.isVertexArrayOES()`](oes_vertex_array_object/isvertexarrayoes)  
Returns `true` if a given object is a [`WebGLVertexArrayObject`](webglvertexarrayobject).

[`ext.bindVertexArrayOES()`](oes_vertex_array_object/bindvertexarrayoes)  
Binds a given [`WebGLVertexArrayObject`](webglvertexarrayobject) to the buffer.

Examples
--------

    var oes_vao_ext = gl.getExtension('OES_vertex_array_object');
    var vao = oes_vao_ext.createVertexArrayOES();
    oes_vao_ext.bindVertexArrayOES(vao);

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

`OES_vertex_array_object`

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

`bindVertexArrayOES`

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

`deleteVertexArrayOES`

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

`isVertexArrayOES`

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

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.vertexAttribPointer()`](webglrenderingcontext/vertexattribpointer)
-   WebGL2 equivalent methods:
    -   [`WebGL2RenderingContext.createVertexArray()`](webgl2renderingcontext/createvertexarray)
    -   [`WebGL2RenderingContext.deleteVertexArray()`](webgl2renderingcontext/deletevertexarray)
    -   [`WebGL2RenderingContext.isVertexArray()`](webgl2renderingcontext/isvertexarray)
    -   [`WebGL2RenderingContext.bindVertexArray()`](webgl2renderingcontext/bindvertexarray)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OES_vertex_array_object" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OES_vertex_array_object</a>
